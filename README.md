# This repo is not hosted on GH, its main home is https://framagit.org/setop/pylufic


# What

**pylufic** is a command line tool which allow to interact with [Let's Upload File (Lufi)](https://demo.lufi.io/about) instances, that is to download and upload client-side encrypted files.

# Why

Lufi is a web-application allowing client-side encrypted file transfers between users. Hence you don't have to trust the service provider to protect your data.

However Lufi works in a web browser, like Firefox or Chormium. When you don't want to run a full-featured graphical web browser on your machine to use it, you need a command line.

**pylufic** is a python implementation of a Lufi CLI, useful for those who already have Python in their environments.

# How

**pylufic** use the same software libraries as the Javascript version - websocket client and Standford Javascript Cryptography Library (SJCL) - but in their python implementations.

# Use


## Help

```
./pylufic.py
```

## Upload

```
./pylufic.py file service_url
```

You may use "https://framadrop.org/" (consider donation).

## download

```
./pylufic.py url
```

Be aware a file is opened in the current directory in append mode with the name provided in the metadata of the transfer.

## delete

To delete a file use link provided by upload function.

An example using curl :

```
curl -s -S 'https://framadrop.org/d/<shortid>/<token>' | html2text
```

# Limitation

**pylufic** handles only one file at a time ; no multi-files upload or download. 
