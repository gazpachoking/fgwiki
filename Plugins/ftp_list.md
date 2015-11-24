
## ftp_list
Generate entries from a remote FTP server
**Configuration:**

    ftp_list:
      config:
        name: <ftp name>
        username: <username>
        password: <password>
        host: <host to connect>
        port: <port>
        [[<no/yes|files-only:]]
        [[<no/yes|recursive:]]
        [[<no/yes>|use-ssl:]]
        [[<auto/utf8/ascii>|encoding:]]
      dirs:
        - <directory 1>
        - <directory 2>
        - ....

