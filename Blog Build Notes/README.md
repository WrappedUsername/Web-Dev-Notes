## First step in blog build, create Hygraph (GraphCMS) schema.
[Build hygraph schema](https://hygraph.com/)
## Models
The schema is defined by the models created, and fields added. Inside the schema editor, add fields, create relationships between models, and much more.

Create a model for author, categories, comments, and the blog post itself. Add the required fields for each model, e.g. single line text for author with a display name of "Name", because the author of the blog post must have a name.

### Field options for "Name"

- Use as title field

Displays this field's value instead of the ID in relations

- Make field required in validations tab

Prevents saving an entry if this field is empty
