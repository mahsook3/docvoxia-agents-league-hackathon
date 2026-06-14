docker compose up

alembic upgrade head

uvicorn app.main:app --reload