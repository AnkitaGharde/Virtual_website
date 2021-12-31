# Virtual_website


Steps for deploy django project on heroku:



1. Create Procfile 

2. Add the below line
    web: python manage.py collectstatic --no-input; gunicorn codingmaster.wsgi --log-file - --log-level debug

3. pip install gunicorn

4. pip install whitenoise

5. Update settings.py
    DEBUG = False
    ALLOWED_HOSTS = ['127.0.0.1','yourdomain.com']

5. Add Moddleware
    'whitenoise.middleware.WhiteNoiseMiddleware',

6. Create Requirements.txt File
    pip freeze > requirements.txt

7. Login to Heroku and create a app

8. Go to settings and add a build type of Python

9. update Settings.py and add domain name in the ALLOWED Host

10. Add these lines to settings.py for static files access
STATIC_URL = '/static/'
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static')
]
STATIC_ROOT = os.path.join(BASE_DIR, 'static_cdn', 'static_root')

10. Git Setup
A. Create a repository in git hub
B. Enter Commands:
    i. git init
    ii. git remote add <repository_url> 
    iii. git add *
    iv. git commit -m <comment>
    v. git push --set-upstream origin master



