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

### User

  - username: string [unique, 4-12 chars, present]
  - email: string [unique, 8 chars minimum, present]

  has_many :pins
  has_many :comments 

### Pins

  - content: string [5 chars minimum, present]
  - user_id: integer [unique, present]

  belongs_to :user
  has_many :comments

### Comments 

  - body: text [4 chars minumum, present]
  - user_id: integer [unique, present]
  - pin_id: integer [unique, present]

  belongs_to :user
  belongs_to :pin


## Exercise 4

### User

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
  - user_id: integer [present]

  belongs_to :user
  has_many :comments

### Comments

  - body: text [present]
  - author_id: integer [present]
  - user_id: integer [present]
  - asks_id: integer [present]
  - show_id: integer [present]

  belongs_to :articles
  belongs_to :user
  belongs_to :asks
  belongs_to :show

### Asks

  - title: string [unique, present]
  - body: text [10 chars minimum, present]
  - user_id: integer [present]

  belongs_to :user
  has_many :answers

### Show

  - title: string [unique, present]
  - website: text [present]
  - user_id: integer [present]

  belongs_to :user
  has_many :comments

### Jobs

  - title: string [unique, present]
  - website: text [present]
  - user_id: integer [present]

  belongs_to :user