Hey team, just a heads up on the W10D2 Collaborative Filtering Model Based Assignment. The scikit-surprise library has a few surprises when it comes to its object data types.
First, the book_ratings dataframe is turned into a Surprise Dataset object.
```Python
# Loads Pandas dataframe
data = Dataset.load_from_df(book_ratings, reader)
type(data)
>>> surprise.dataset.DatasetAutoFolds
```
Next, the data is split 85/15 into different trainset and testset objects.
```Python
trainset, testset = train_test_split(data, test_size=0.15)
type(trainset)
>>> surprise.trainset.Trainset
type(testset)
>>> list
```
Note the 3 different data types. These cause some trouble since GridSearchCV only fits on a dataset object.
```Python
# Standalone models fit on a trainset object
SVD().fit(trainset)
# Gridsearch models fit on a dataset object
GridSearchCV(SVD),fit(data)
```
Passing a trainset object to GridSearch raises an `AttributeError`. See Surprise author Nicolas Hug's response (https://github.com/NicolasHug/Surprise/issues/190)
See documentation for "hacky" implementation of GridSearchCV with split data (https://surprise.readthedocs.io/en/stable/FAQ.html#unbiased-estimate-after-tuning)

The solution I came to was to split the dataframe into train and test sets before creating two surprise datasets. Then I applied the `build_full_trainset()` and `build_testset()` methods. See the respective documentation : (https://surprise.readthedocs.io/en/stable/dataset.html?highlight=build_full_trainset#surprise.dataset.DatasetAutoFolds.build_full_trainset ) and (https://surprise.readthedocs.io/en/stable/trainset.html?highlight=build_testset#surprise.Trainset.build_testset)



Heads up on the Topic Modeling Walkthrough.
When the tutorial gets to the last part of section 4 "Remove Stopwords and Lemmatize tokens" the implementation of Spacy Lemmatization has changed.

From Spacy 3.2 Documentation https://spacy.io/models/en#en_core_web_sm
Doing a pip install from github has been replaced by the CLI command
```python -m spacy download en_core_web_sm```
This downloads `en_core_web_sm 3.2.0` to your pip packages list, which you can verify with `pip list`.
To load it in jupyter use the line
```Python
nlp = spacy.load("en_core_web_sm")
```



To download data for the Sentiment Analysis walkthrough:
Follow the instructions in the [documentation](https://github.com/Kaggle/kaggle-api) to set up the Kaggle API.

When saving the credentials file to `~/.kaggle/kaggle.json` you first need to make the directory
`mkdir ~/.kaggle`

Accept the rules of the UMICH SI650 - Sentiment Classification competition [here](https://www.kaggle.com/c/si650winter11/rules). Files will not download without accepting the rules.

`kaggle competitions download -p ~/path/to/save/files -c si650winter11` omitting the -p flag save the files to the present working directory.



For MacOS users, an equivalent alternative to WinSCP is called Cyberduck. Here's how you can set it up.

Secure File Transfer Protocol (SFTP) with Cyberduck (compatible for MacOS and Windows)
Install

- https://cyberduck.io/download/
- On MacOS `brew install --cask cyberduck`
- Cyberduck is free but will prompt for donations. To disable the prompt, a registration key can be purchased from the link above or the app can be purchased from the Mac App Store

Connect to AWS EC2 Instance with Cyberduck 8.2.1

- Open Cyberduck
- Open Connection
- SFTP (SSH File Transfer Protocol)
```Python
  Server : <Public IPv4 DNS>,
  Port : 22  # Default,
  Username : 'ec2-user' or 'ubuntu',  # depends on Amazon Machine Image
  Password : <blank>,
  SSH Private Key : /path/to/key.pem
```
- Connect

Once connected, you can disconnect using the Disconnect button at the top of the window.
Connections are saved in the Bookmarks list

Process adapted from the [tutorial by Jhonny Fransis](https://www.youtube.com/watch?v=hd4oL3WIPVM)



Hi Cody, I'm on MacOS and did get connect to the instance. @theaiwhisperer#3570 and @ericelmo#2522 helped me through nearly every step. I wrote out detailed instructions for my process through the 3 compass tutorials.

#### Start AWS Instance

- From [AWS EC2 Dashboard](https://ca-central-1.console.aws.amazon.com/ec2/v2/home?region=ca-central-1#Home:)
- Set the appropriate region (e.g. ca-central)
- Launch Instance
- Choose Amazon Machine Image (AMI) (e.g. Ubuntu 20.04)
- Choose type (e.g. free tier t2.micro)
- Configure security group (skip steps 3–5)
  - Add inbound rules (e.g. Type: All Traffic, Source: Anywhere-IPv4, this is very insecure) This is the firewall and determines who can connect to your virtual machine. Give your own IP address permission.
- Review and Launch
- Create new key or connect an existing one
  - An existing key may be automatically connected
  - When creating a new permission key
    - save the `.pem` file somewhere secure
    - permissions may need to be modified from the CLI with `chmod 400 <file>`
- Launch
- Connect to AWS instance in CLI
  - `ssh -i /path_to_key/lighthouse.pem  ubuntu@<Public IPv4 DNS>`
    - `.pem` is stored on your computer
    - The Public IPv4 DNS is found at EC2/Instances/\<Instance>/Instance Summary/Public IPv4 DNS
#### Set up Anaconda3 for Data Science

- After connecting to instance 
  - Download Aanaconda3 on the instance
    - CLI `curl -O https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh` More recent versions of Anaconda3 do not seem to be compatible with Ubuntu 20.04.
  - Install Anaconda3 on instance
    - CLI `sh Anaconda3-2020.02-Linux-x86_64.sh`
      - hold down `return` to progress through the license agreement and type `yes` to agree
      - Once the installation asks: `Do you wish the installer to initialize Anaconda3 by running conda init?` Select yes
  - Restart instance by typing `exit` and reconnecting

#### Using Jupyter

- Create tmux session
  - Instance CLI `tmux new -s <session_name>`
- Instance CLI `jupyter lab --ip 0.0.0.0 --port 8888 --no-browser`
  - Returned is an html file and two URLs
  - The URLs end with `token=<token>`
- In local browser navigate to `http://<Public IPv4 DNS>:8888/lab`
  >The port number `8888` could be anything but it has to mach in both commands.
  - The first time connecting will prompt for the `<token>` of the previous step
- To disconnect from instance and leave jupyter session running
  - detach from tmux session `[ctrl+b]` `[d]`
  - disconnect from instance `exit`
- To reattach to running jupyter session
  - Instance CLI `tmux a -t <session_name>`



  