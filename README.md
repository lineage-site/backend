# backend

# Heroku Setup
```sh
brew tap heroku/brew
brew install heroku
heroku login
```
## Allow direnv to manage environment variables
```sh
brew install direnv
direnv allow
```

# Python Setup
```sh
brew install pipenv
pipenv install
```

# Postgres Setup
```sh
brew install postgres
createdb lineage_dev
psql -c "create role lineage_dev with login password 'lineage_dev'; grant all privileges on database lineage_dev TO lineage_dev;" lineage_dev
# Add database settings to direnv:
echo "export DATABASE_URL=postgres://lineage_dev:lineage_dev@localhost/lineage_dev" >> .envrc; direnv allow
