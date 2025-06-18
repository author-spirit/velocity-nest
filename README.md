# velocity-NEST
Learning platform provides spaced-repetition, visual learning & contests

## Components
### Backend
- Python3 (FlaskAPI)

### Datasource
- Postgres (JSON Support, RAG)

### Frontend
- VueJS3
- Flutter (Planned)

# Schema
## Deck
- id | Int | Primary Key
- title | String | Deck title 
- mode | enum | flashcard/quiz
- owner | Foreign Key | User
- description | Text | Markdown
- tags | JSON
- created_time | timestamp
- modified_time | timestamp
- is_draft | boolean

## card
- id | Int | Primary Key
- deck_id | Foreign Key | Deck
- (optional) type	| enum	flashcard / mcq / code / interactive
- question	| Text	| The question text or prompt
- answers	| JSONB	| One or multiple answers, depending on type
- explanation	| Text	| Optional explanation
- order	| Int	| Position in deck
- difficulty | Enum | easy/medium/hard
- created_time | timestamp
- modified_time | timestamp
