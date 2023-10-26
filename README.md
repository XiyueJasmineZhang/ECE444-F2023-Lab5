# ECE444-F2023-Lab5

Referencing code from https://github.com/mjhea0/flaskr-tdd

Sections completed:
1. First Test
2. Database Setup
3. Templates and Views
4. Add Some Style
5. JavaScript
6. Bootstrap
7. SQLAlchemy
8. 

Unit Test Added:
```
def test_search(client):
    """Test searching for posts"""
    with app.app_context():
        new_entry1 = Post("Cat", "This is a test entry 1.")
        new_entry2 = Post("Dog", "This is a test entry 2.")
        db.session.add(new_entry1)
        db.session.add(new_entry2)
        db.session.commit()

    query = "Cat"
    rv = client.get(f"/search/?query={query}")
    assert query.encode() in rv.data
    assert b"This is a test entry 1." in rv.data
```