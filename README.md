Local provisioning for getting started with ruby development
====================

Based on the blog post [here](http://marvelley.com/blog/2014/04/11/local-provisioning-with-ansible/).

Steps:
Install xcode command line tools:

```
xcode-select --install
```

On your computer, you first need ansible.  Best way to install on the mac is:

```
sudo bash -c 'curl https://bootstrap.pypa.io/ez_setup.py -o - | python'
sudo easy_install pip
pip install ansible
```
If you have problems installing pip, you may want to download and use [this python](https://www.python.org/ftp/python/2.7.12/python-2.7.12-macosx10.6.pkg). Once installed, go to the python folder in your applications and click the `Update Shell Profile.command` file.  Instead of the above commands, run simply `pip install ansible`.

You also need to [generate a keypair](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) and add it to your github, as this script clones my [dotfiles repo](https://www.github.com/dgliwa/dotfiles)

Clone this repo and run the setup by running the following:

```
git clone git@github.com:dgliwa/setup_ruby.git
```

Open the `playbook.yml` file and change the name, email, and github_username to your information.

```
cd ./setup_ruby
ansible-playbook -i "localhost," -c local playbook.yml
```

Now you should be ready to go. You will probably want to open a new terminal window to see all the changes.
