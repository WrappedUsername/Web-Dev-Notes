## First step in blog build, create Hygraph (GraphCMS) schema.
[Build hygraph schema](https://hygraph.com/)
## Models
The schema is defined by the models created, and fields added. Inside the schema editor, add fields, create relationships between models, and much more.

Create a model for author, categories, comments, and the blog post itself. Add the required fields for each model, e.g. single line text for author with a display name of "Name", because the author of the blog post must have a name.

## Author model

### Field options for "Name" - Single line text

- Use as title field

Displays this field's value instead of the ID in relations

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Field "Avatar" - Asset picker

- Not required

### Field "Bio" - Multi line text

- Not required

## Category model

### Field options for "Name" - Single line text

- Use as title field

Displays this field's value instead of the ID in relations

- Make field required in validations tab

Prevents saving an entry if this field is empty

- Set field as unique

Ensures that a multiple entries can't have the same value for this field

### Field options for "Slug" - Slug

- Lowercase

Converts the slug to lowercase characters

- Make field required

Prevents saving an entry if this field is empty

- Set field as unique

Ensures that a multiple entries can't have the same value for this field

- Match a specific pattern

Only accepts specified regular expression (e.g. e-mail, URL)
