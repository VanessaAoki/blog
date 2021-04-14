## Exercise 1

### Courses

  - title: string [unique, 4-12 chars, present]
  - description: text [10 chars minimum, present]

  has_many :lessons

### Lessons

  - title: string [unique, 4-12 chars, present]
  - body: text [10 chars minimum, present]
  - course_id: integer [present]

  belongs_to :courses


## Exercise 2

### User

  - username: string [unique, 4-12 chars, present]
  - email: string [unique, 8 chars minimum, present]

  has_one :geographic_profile
  has_one :personal_profile

### Geographic profile

  - city: string [3 chars minumin, present]
  - state: string [3 chars minimun, present]
  - country: string [3 chars minumum, present]
  - user_id: integer [unique, present]

  belongs_to :user

### Personal profile

  - age: integer [present]
  - gender: string [4-12 chars]
  - user_id: integer [unique, present]

  belongs_to :user
  

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