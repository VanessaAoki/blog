## Exercise 1

### Courses

  - title: string [unique, 4-12 chars, present]
  - description: text [10 chars minimum, present]

  has_many :lessons

### Lessons

  - title: string [unique, 4-12 chars, present]
  - body: text [10 chars minimum, present]

  belongs_to :courses
  

## Exercise 2

## Exercise 3


## Exercise 4

### Author

  - username: string [unique, 4-12 chars, present]
  - password: string [6-12 chars, present]

  has_many :articles
  has_many :comments
  has_many :asks
  has_many :show
  has_many :jobs

### Articles

  - title: string [unique, present]
  - website: text [present]
  - author_id: integer [present]

  belongs_to :author
  has_many :comments

### Comments

  - body: text [present]
  - author_id: integer [present]
  - article_id: integer [present]

  belongs_to :articles
  belongs_to :author
  belongs_to :asks
  belongs_to :show

### Asks

  - title: string [unique, present]
  - body: text [10 chars minimum, present]
  - author_id: integer [present]

  belongs_to :author
  has_many :answers

### Show

  - title: string [unique, present]
  - website: text [present]
  - author_id: integer [present]

  belongs_to :author
  has_many :comments

### Jobs

  - title: string [unique, present]
  - website: text [present]
  - author_id: integer [present]

  belongs_to :author