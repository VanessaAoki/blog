## Authors
  - username: string [unique, 4-12 chars, present]
  - password: string [6-12 chars, present]
  - id: integer [unique, present]

  has_many Article
  has_many Comments

## Article

  - title: string [unique, present]
  - body: text [10 chars minimum, present]
  - website: string [present]
  - author_id: integer [present]
  - id: integer [unique, present]

  belongs_to Author
  has_many Comments

## Comments

  - body: text [present]
  - author_id: integer [present]
  - article_id: integer [present]
  - id: integer [unique, present]

  belongs_to Article
  has_one Author