### Install dependency 
```
pip install fastapi uvicorn sqlalchemy graphene graphene-sqlalchemy alembic psycopg2 black python-dotenv 
```

### Setup database migration
```
alembic init 
```
```
docker-compose run app alembic revision --autogenerate -m "New Migration" 
docker-compose run app alembic upgrade head 
```

### GraphQL 

GraphQL mutation: 
```
mutation createNewPost{
    createNewPost(title:"new title1",content:"new content"){
        ok
    }
}
```

GraphQL query: 
```
query{
    allpost{
        title
    }
}
```

```
query{
    postById(postId:2){
        id
        title
        content
    }
}
```