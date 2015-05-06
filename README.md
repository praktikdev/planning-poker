# Planning Poker

## Summary

Planning Poker is a web platform allowing users to perform scrum task time estimation votings, organized in virtual rooms. Its back-end is powered by Django framework. After registration, the user gets access to a customized django admin panel where they can manage their rooms and participants, who gain access by personalized URLs.

The voting data is transferred between clients using websockets (socket.io). Application's front-end is based on Twitter Bootstrap and a custom Angular.js engine. 

Planning Poker offers JIRA integration simplifying the process of fetching lists of tasks from current JIRA sprint.

## Demo

You can create a fully-featured demo room without registration here: [http://planningpoker.prktk.pl/demo/](http://planningpoker.prktk.pl/demo/)

In case you want to check out the full expirience, you might register an admin account by visiting: [http://planningpoker.prktk.pl/register/](http://planningpoker.prktk.pl/register/) - credentials achieved by signing up may be used to login into the administration interface available at the url: [http://planningpoker.prktk.pl/admin/](http://planningpoker.prktk.pl/admin/).

**Note**: all user created data on our test instance is wiped out once a day, at 12am GMT+2.

## Installation

In order to run your own instance of planning poker:

1. Clone the repo:

 ```bash
git clone https://github.com/praktikdev/planning-poker.git
```

1. Create virtualenv:

 ```bash
virtualenv env
```

1. Activate it:

 ```bash
. env/bin/activate
```

1. cd the app directory:

 ```bash
cd planning-poker
```

1. Install requirements:

 ```bash
pip install -r requirements.txt
```

1. Create your copy of `local_settings.py` and fill it:

 ```bash
cp poker/local_settings.py.dist poker/local_settings.py && vim poker/local_settings.py
```

1. Create your copy of `constants.js`:

 ```bash
cp app/static/scripts/constants.js.dist app/static/scripts/constants.js
```

1. Migrate the database:

 ```bash
python manage.py migrate
```

1. Create your user account:

 ```bash
python manage.py createsuperuser
```

1. Run http and websocket servers:

 ```bash
python manage.py runserver &
python runserver.py &
```

1. Navigate over to [http://localhost:8000/admin](http://localhost:8000/admin) to create your first planning poker room!

## License

This project is licensed under the terms of the MIT license.

## Contributing

Fork the project, create a feature branch, and send us a pull request.