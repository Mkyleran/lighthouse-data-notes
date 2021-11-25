# W1D3-04 Notes
## Today: APIs

[Foursquare Developer](https://foursquare.com/developers/projects)

[Twitter Developer](https://developer.twitter.com/en/portal/dashboard)

### Lecture
Converting from JSON. map() will be cleaner and more efficient

Download a JSON formatting web extension

### Work

Store sensitive information like API keys in environment variables.
`export ENV_VAR_NAME=value` creates a temporary environment variable local to the terminal session. To make them permanent read [Create permanent environment variables](https://www.sudhanshutheone.com/posts/environment-variables-mac)

[StackExchange](https://apple.stackexchange.com/questions/356441/how-to-add-permanent-environment-variable-in-zsh) to set permanent environment variables in Zsh.

__Geewhiz...__
In order to access permanent environment variables stored in .bash_profile in jupyter lab:
1. `source ~/.bash_profile` Probably because bash is not default, it doesn't source .bash_profile. .bash_profile stores permanent environment variables and initiates conda.
2. `conda activate <dev_env>` activate the conda environment
3. `jupyter lab` launch jupyter lab