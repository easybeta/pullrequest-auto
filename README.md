github-autopullrequest.py
================

This script helps automate code reviews of pull requests to a specified GitHub repositories.
Using the GitHub api (documented at https://api.github.com/) the script will scan the 
currently open pull requests for a specified working directory and reports whether or not 
the open pull request contain 'interesting items', which will be specified in config file 
titled "interesting-config.json".

Examples of Interesting Items:
- Any change to the specified files
- Does not contain changes to any files in the specified directory
- Any added or deleted lines contain the follow words (not as substrings of larger words):
/dev/null<br>
raise<br>
.write<br>

Example:
> review puppetlabs/puppet <br>
> https://github.com/puppetlabs/puppet/pull/16663 - Interesting <br>
> https://github.com/puppetlabs/puppet/pull/16600 - Not Interesting <br>
> https://github.com/puppetlabs/puppet/pull/16598 - Not Interesting <br>
