1. Generate secret key by command:

    ```docker-compose run --rm sentry config generate-secret-key```

   or

    ```pwgen 60```

   or invite your cat.

1. Set the output to `SENTRY_SECRET_KEY` variable in sentry-variables.env.

1. If you want Sentry to send emails (member invitations or error notifications) set up email configuration variables.

1. It is the initial start of Sentry container, so DB sync is needed, run:

    ```docker-compose run sentry upgrade```

1. While running this command user creation will be offered. Set your email and pass to access Sentry.

    ```Would you like to create a user account now? [Y/n]:
    Email:
    Password:
    Repeat for confirmation:
    ```

1. Agree to be a superuser:

    ```Should this user be a superuser? [y/N]: Y```

1. Final command to start Sentry:

    ```docker-compose up -d```

Sentry is on 8080 port, you can change it in docker-compose.yml.

Open Sentry, login, set root url.

Then add members in:

    http://<host>:8080/organizations/sentry/members/new/

Used Sentry image:
https://hub.docker.com/_/sentry/
Sentry is awesome, thanks!
