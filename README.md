# Secrets

This repository uses [blackbox] to work with secrets. Please visit [blackbox]
for installation information.

## Quickstart


### Viewing a file:

```sh
blackbox_cat foo.md.gpg
```


### Editing a file:

```sh
blackbox_edit_start foo.md.gpg
# EDIT foo.md
blackbox_edit_end foo.md.gpg
```


### Adding a new file:

```sh
blackbox_register_new_file foo.md
```


### Removing a file:

```sh
blackbox_deregister_file foo.md
```


### Requesting access to view/edit this repo

Submit a PR after completing the following steps:

1. Set up a new GPG key:

    ```sh
    gpg --gen-key
    ```

2. Add your key to the blackbox keyring (where KEYNAME is the email you created
   the key with):

    ```sh
    blackbox_addadmin KEYNAME
    ```

3. Commit the changes using the recommended commit message provided by
   blackbox.


### Adding a new user to the repo (for admins)

1. Verify new keys:

    ```sh
    gpg --homedir=keyrings/live --list-keys 
    ```

2. Import new keys to your local keyring

    ```sh
    gpg --import keyrings/live/pubring.gpg
    ```

3. Reencrypt files with new key

    ```sh
    blackbox_update_all_files
    ```

4. Commit changes and update repo.


[blackbox]: https://github.com/StackExchange/blackbox
