# ECE444-F2023-Lab5

Referencing code from https://github.com/mjhea0/flaskr-tdd

### Sections completed:
1. First Test
2. Database Setup
3. Templates and Views
4. Add Some Style
5. JavaScript
6. Bootstrap
7. SQLAlchemy
8. Search Page
9. Login Required
10. Linting and Code Formatting

### Screenshot of Final Website:
![website](images/website.png)

### Unit Test Added:
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

### Linting and Code Formatting Completed:
![reformat 1](images/reformat1.png)
![reformat 2](images/reformat2.png)

### What are the pros and cons of TDD?
The pros of TDD include:
- Early detection of bugs: having tests writen before/around the same time as the code makes it easier to catch bugs early on. This reduces technical debt as the longer a bug goes undetected, the more time and resources it could take to fix later.
- Regression testing: since all the tests are run at once (kind of like e2e) after code changes, you can also make sure that previously working functionality remains intact. This is especially helpful as an application grows in size/features.
- General improvement of code quality: TDD faciliates clearer and more maintainable code that is well-structured and modular (as this helps with tests).

The cons of TDD include:
- Initial overhead: writing tests for code slows down initial development and can be tedious.
- Maintaining and adding tests: requires a lot of time as well, which can slow down general development.
- Required skills in test development: a gap in test coverage can lead to a false sense of security about the application and lead to critical issues being missed.