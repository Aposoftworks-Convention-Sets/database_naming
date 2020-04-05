# Database naming
This set will help you name the columns, tables and even the database itself in your projects. We are going to use hierarchy_case for the naming convention here. You can read about it [here](https://github.com/Aposoftworks-Convention-Sets/hierarchycase).

## What it is
As a programmer, you often know the stress of trying to guess what you are dealing with when encountering a variable from a model. If it's an object, array, a relationship or just a column. With the help of the hierarchy case, we can achieve a really readable and organized database for that.

## How to use it
- With the database names, the function of the name (the first word to come) is going to be the framework the database is dealing with. You can reduce the name to a state identifiable for you. For example, laravel can become lrvl.
``` SQL
lrvl_ecommerce
wp_blog
cake_site
ci_api
```

- We divide the tables in three categories: core, data and links. We put them at the start, in the place of the function.

Core represents data that is important for the application functionality, such as languages available, metrics or analytics.
Data is what the user has created, for example data_post.
Link is a literal link between data or core. For example, member, that could link a data_group and a data_user.
``` SQL
core_languages
data_user
data_group
link_member
```

- In the columns, you use hierarchy case exactly as described in it's rules. Once again, you can read about it, [here](https://github.com/Aposoftworks-Convention-Sets/hierarchycase). Don't forget that we are inside of the context of the table, so we can hide the name if it matches the context, such as: id_user could become id, because we are inside of the user context.
``` SQL
id
data
id_user_created
id_user_updated
date_created
date_updated
```

## Examples
We are going to create a database for laravel for a simple blog
### database name
lrv_blog

### Tables
core_tag
- id
- label
- description
- date_created
- date_updated
- id_user

data_user
- id
- name
- email
- date_created
- date_updated
- date_verified

data_post
- id
- label
- data
- date_created
- date_updated
- id_user

link_owner
- id_user
- id_post
