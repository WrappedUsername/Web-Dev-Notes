## First step in blog build, create Hygraph (GraphCMS) schema.
[Build hygraph schema](https://hygraph.com/)
## Models
The schema is defined by the models created, and fields added. Inside the schema editor, add fields, create relationships between models, and much more.

Create a model for author, categories, comments, and the blog post itself. Add the required fields for each model, e.g. single line text for author with a display name of "Name", because the author of the blog post must have a name etc.

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

- Set field as unique in validations tab

Ensures that a multiple entries can't have the same value for this field

### Field options for "Slug" - Slug

- Lowercase

Converts the slug to lowercase characters

- Make field required in validations tab

Prevents saving an entry if this field is empty

- Set field as unique in validations tab

Ensures that a multiple entries can't have the same value for this field

- Match a specific pattern in validations tab

Only accepts specified regular expression (e.g. e-mail, URL), set to slug.

## Comment model 

### Field options for "Name" - Single line text

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Field options for "Email" - Single line text

- Make field required in validations tab

Prevents saving an entry if this field is empty

- Match a specific pattern

Only accepts specified regular expression (e.g. e-mail, URL), set to email.

### Field options for "Comment" - Markdown

- Make field required in validations tab

Prevents saving an entry if this field is empty

## Post model

### Field options for "Title" - Single line text

- Use as title field

Displays this field's value instead of the ID in relations

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Field options for "Slug" - Slug

- Lowercase

Converts the slug to lowercase characters

- Make field required in validations tab

Prevents saving an entry if this field is empty

- Set field as unique in validations tab

Ensures that a multiple entries can't have the same value for this field

- Match a specific pattern in validations tab

Only accepts specified regular expression (e.g. e-mail, URL), set to slug.

### Field options for "Excerpt" - Multi line text

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Field options for "Content" - Markdown

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Field "Featured Image" - Asset picker

- Not required

### Field options for "Featured Post" - Boolean

- Make field required in validations tab

Prevents saving an entry if this field is empty

### Create reference field

- Define relationship

### Reference type

- Allow only one model to be referenced

Field can return content from one model

- Model to reference - "Author"

### Reference direction

- Two-way reference

Creates a reverse field to query content from both sides

### Relation cardinality - Many to one

- Allow multiple Posts per Author

### Reference type

- Allow only one model to be referenced

Field can return content from one model

- Model to reference - "Category"

### Reference direction

- Two-way reference

Creates a reverse field to query content from both sides

### Relation cardinality - Many to many

- Allow multiple Posts per Category

- Allow multiple Categories per Post










