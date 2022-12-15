# GPG

## Add email to key

1.
    ```bash
    gpg --edit-key <key id>
    ```

1.
    ```bash
    adduid
    ```
    ```
    Real Name: OCTOCAT
    Email address: "octocat@github.com"
    Comment: GITHUB-KEY
    Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit?
    ```

    **NOTE**: Do not forget to add a passphrase

1.
    ```bash
    save
    ```

1.
    ```bash
    # Prints the GPG key, in ASCII armor format
    # Upload it to GitHub, GitLab, etc.

    gpg --armor --export <key id>
    ````

## Remove `uid` from key

1.
    ```bash
    gpg --edit-keys <key id>
    ```

1.
    ```bash
    uid <id>
    ```

1.
    ```bash
    revuid
    ```

1.
    ```bash
    save
    ```

1.
    ```bash
    gpg --send-keys <key id>
    ```
