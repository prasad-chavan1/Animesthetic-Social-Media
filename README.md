# Animesthetic Social Media Web App Project

<p align="center">
<a href="https://github.com/prasad-chavan1/Animesthetic-Social-Media/blob/main/LICENSE" target="blank">
<img src="https://img.shields.io/github/license/prasad-chavan1/Animesthetic-Social-Media?style=for-the-badge&logo=appveyor" alt="github-profile-readme-generator license" />
</a>
<a href="https://github.com/prasad-chavan1/Animesthetic-Social-Media/fork" target="blank">
<img src="https://img.shields.io/github/forks/prasad-chavan1/Animesthetic-Social-Media?style=for-the-badge&logo=appveyor" alt="github-profile-readme-generator forks"/>
</a>
<a href="https://github.comprasad-chavan1/Animesthetic-Social-Media/stargazers" target="blank">
<img src="https://img.shields.io/github/stars/prasad-chavan1/Animesthetic-Social-Media?style=for-the-badge&logo=appveyor" alt="github-profile-readme-generator stars"/>
</a>
</p>

Welcome to the Animesthetic Social Media Web App project! This Django-based web application allows users to connect with friends, share updates, and engage in social networking activities. This README.md file will guide you through the steps to run this app on your local machine.


## Table of Contents

- [Getting Started](#getting-started)
   - [Setting up Postgres User](#setting-up-postgres-user)
   - [Setting up Postgres Database](#setting-up-postgres-database)
   - [Setting up Project](#setting-up-project)
- [Contribution](#contribution)
- [Contributors](#contributors)
- [License](#license)
- [Contact](#contact)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- [Python](https://www.python.org/) (3.6 or higher) installed on your system.
- [Django](https://www.djangoproject.com/) (3.2 or higher) installed.
- [PostgreSQL](https://www.postgresql.org/)
- [Git]()

## Getting Started

To started working with the project, you need to setup [Postgres Database](#setting-up-database) and [Project](#setting-up-project) which are explained below:

### Setting up Postgres User

1. First, make sure that postgres server is running by `systemctl start` command.

   ```bash
   sudo systemctl start postgresql.service
   ```

2. Then, you can switch to the postgres account by typing

   ```bash
   sudo -i -u postgres
   ```

3. We can create a new role(user) from the command line with the `createuser` command along with `--interactive` flag.

   ```bash
   postgres@server:~$ createuser --interactive
   ```

   _Note: `postgres@server:~$` is the prompt and `createuser --interactive` is the command_`

   The script will prompt you with some choices and, based on your responses execute the correct Postgres commands to your specifications:

   ```
   Output
   Enter the name of role to add: test_user
   Shall the new role be a superuser?(y/n) y
   ```

   _Note: Above is just a example it might be different for you. \*\*Make sure that that role(user) you have created is superuser._

4. Now, its time to add password to created user using `\password test_user`. Execute psql command to prompt into postgres server.

   ```bash
   postgres@server:~$ psql
   ```

   Then you will be prompt to

   ```bash
   postgres=#
   ```

   Type `\password test_user` command and execute.

   ```bash
   postgres=# \password test_user
   ```

   YOu will be prompter to enter and confirm a pasword. Now, exit the PostgreSQL interface using `\q` and exit back to your normal user.

5. Creating database of the user we have created.

   ```bash
   postgres@server:~$ createdb sammy
   ```

[References](https://www.digitalocean.com/community/tutorials/how-to-use-roles-and-manage-grant-permissions-in-postgresql-on-a-vps-2)

### Setting up Postgres Database

1. To create a database for **Animesthetic Scoal Media Web App** we can use `createdb <database_name>` as before.

   ```bash
    postgres@server:~$ createdb social_network
   ```

   _Note: For this project i have created `social_network` database you might create different for you._

[References](https://www.digitalocean.com/community/tutorials/how-to-install-postgresql-on-ubuntu-20-04-quickstart)

### Setting up Project

1. Clone this repository to your local machine using the following command:

   ```bash
   git clone https://github.com/yourusername/Animesthetic-Social-Media.git
   ```

2. Then go to Social App directory using command:

   ```bash
   cd Social-Network
   ```

3. Install the required librarys using command:

   ```bash
   pip install -r requirements.txt
   ```

4. Create `.env` file

   ```bash
   touch .env
   ```

5. Add the following lines

   ```env
   DB_NAME=social_network
   DB_USERNAME=test_user
   DB_PASSWORD=test_user
   DB_HOST=localhost
   DB_PORT=5432
   ```

   <i>
   Note: 
      DB_NAME=database name you have created
      DB_USERNAME=roles(user) name you have created
      DP_PASSWORD= password for that user you have created

   </i>

6. Running migrations

   ```bash
   python3 manage.py makemigrations
   python3 manage.py migrate
   ```

7. Create Super User by using command:

   ```bash
   python3 manage.py createsuperuser
   ```

8. Run the app on local machine using command:

   ```bash
   python manage.py runserver
   ```

9. Enter details and good to go 😄 go to following url in your browser:

   ```bash
   http://127.0.0.1:8000/admin
   ```

## Contribution

We welcome contributions! If you'd like to contribute to this project, please read our [Contributing Guidelines](CONTRIBUTING.md) for instructions on how to get started.

## Contributors

Thank you to the following contributors who have helped improve this project:

- [Prasad Chavan](https://github.com/prasad-chavan1)

![](https://github.com/Ekata2003/codeWave.github.io/blob/main/itachiDesc.png?raw=true)


## License

This project is licensed under the [MIT License](./LICENSE).

## Contact

If you have any questions or need assistance, feel free to contact us.
