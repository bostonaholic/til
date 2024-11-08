# `HAVING`

:bulb: `HAVING` is a SQL filter similar to `WHERE`.

- `WHERE` filters rows _before_ grouping.
- `HAVING` filters rows _after_ grouping.

**Query:**

Find registered users with more than one pet.

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
| 1  | <alice@example.com> | 5 |
| 2  | <bob@example.com>   | 6 |
| 3  | NULL                | 7 |
| 4  | <alice@example.com> | 8 |

**Result:**

| email | count |
|-------|-------|
| <alice@example.com> | 2 |

:tada: Happy coding!
