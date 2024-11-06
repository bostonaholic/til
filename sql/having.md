# `HAVING`

:bulb: `HAVING` is a SQL filter similar to `WHERE` except that it filters rows _after_ grouping and `WHERE` filters rows _before_ grouping.

**Query:**

Find users with more than one pet.

```sql
SELECT email, count(*)
FROM user_pets
WHERE email IS NOT NULL
GROUP BY email
HAVING count(*) > 1
```

**Data:**

| id | email | pet_id |
|----|-------|--------|
| 1  | <alice@example.com> | 4 |
| 2  | <bob@example.com>   | 5 |
| 3  | <alice@example.com> | 6 |

**Result:**

| email | count |
|-------|-------|
| <alice@example.com> | 2 |

:tada: Happy coding!
