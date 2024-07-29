### 1. Numeric Types

```sql
CREATE TABLE example_table (
    id INT,
    price DECIMAL(10, 2),
    age TINYINT UNSIGNED
);```

- INT: An integer number.
- DECIMAL(M, D): A decimal number with total digits M and digits after the decimal point D.
- TINYINT UNSIGNED: An unsigned tiny integer (0 to 255).

### 2. Character Types

```sql
CREATE TABLE example_table (
    name CHAR(50),
    description VARCHAR(255),
    bio TEXT
);```

- CHAR(n): A fixed-length character string.
- VARCHAR(n): A variable-length character string.
- TEXT: For storing long-form text.

### 3. Date/Time Types

```sql
CREATE TABLE example_table (
    birthdate DATE,
    start_time TIME,
    event TIMESTAMP
);```

- DATE: Stores year, month, and day.
- TIME: Stores hour, minute, and second.
- TIMESTAMP: Stores both date and time.

### 4. Binary Types

```sql
CREATE TABLE example_table (
    image BLOB,
    document LONGBLOB
);```

- BLO: For storing binary data.
- LONGBLOB: For storing large binary objects.

### 5. Boolean Type

```sql
CREATE TABLE example_table (
    is_active BOOLEAN
);```

- BOOLEAN: True or False.

### 6. Enumeration Types

MySQL does not have a built-in ENUM type, but it can be emulated using a set of predefined constants.

```sql
CREATE TYPE example_enum AS ENUM ('value1', 'value2');

CREATE TABLE example_table (
    status example_enum
);```

### 7. Geospatial Types

MySQL supports geospatial data types through spatial extensions.

```sql
CREATE TABLE example_table (
    location POINT
);```

- POINT: Represents a point in space.

### 8. JSON Types

```sql
CREATE TABLE example_table (
    profile JSON
);```

- JSON: Stores JSON formatted text.

### 9. UUID Types

```sql
CREATE TABLE example_table (
    uuid CHAR(36)
);
```

- CHAR(36): Typically used to store UUIDs.

### 10. Array Types

MySQL does not natively support array data types. Arrays can be simulated using other data structures or by using JSON columns.

### 11. Hstore Types

MySQL does not have a direct equivalent to PostgreSQL's hstore. However, similar functionality can be achieved using JSON or custom-defined tables.
# Quantifiers

Quantifiers are used to define the number of times a certain pattern should repeat within a string. They come in various forms, each specifying a different range of repetition:

1. *** (Zero or more)**: Matches the preceding element zero or more times. For example, a* matches "a", "aa", "aaa", " etc.

2. **+ (One or more)**: Matches the preceding element one or more times. For example, a+ matches "a", "aa", "aaa", but not "".

3. **? (Zero or one)**: Matches the preceding element zero or one time, making it optional. For example, a? matches "a" and "".

4. **{n}**: Matches exactly n occurrences of the preceding element. For example, a{3} matches "aaa".

5. **{n,}**: Matches n or more occurrences of the preceding element. For example, a{2,} matches "aa", "aaa", "aaaa", etc.

6. **{n,m}**: Matches between n and m occurrences of the preceding element. For example, a{2,3} matches "aa" and "aaa".
### Existential Quantifier (∃)

- **Definition:** The existential quantifier asserts that there exists at least one tuple in a relation that satisfies a given condition.
- **Syntax:** ∃x P(x), where x is a variable ranging over the domain of discourse, and P(x) is a predicate that describes a property or condition.
- **Usage:** Used to express that a certain property holds true for at least one element in a set. For example, ∃x (Student(x) ∧ Age(x) > 18) states that there exists a student who
 is older than 18.

### Universal Quantifier (∀)

- **Definition:** The universal quantifier asserts that for all tuples in a relation, a given condition holds true.
- **Syntax:** ∀x P(x), where x is a variable ranging over the domain of discourse, and P(x) is a predicate that describes a property or condition.
- **Usage:** Used to express that a certain property holds true for every element in a set. For example, ∀x (Student(x) → Age(x) ≥ 18) states that for all students, their age is
 greater than or equal to 18.

### Cardinality Quantifiers

Relational algebra also employs quantifiers to specify the number of tuples that satisfy a condition:

- **Some Quantifier (⋎)**: Represents "there exists" and is used similarly to the existential quantifier. It asserts that there is at least one tuple satisfying a given condition.
- **All Quantifier (⋊)**: Represents "for all" and is used similarly to the universal quantifier. It asserts that for all tuples, a given condition holds true.

These quantifiers are particularly useful in expressing conditions in selection operations, where you might want to select tuples based on whether certain properties hold for at
 least one or all tuples in a relation.

### Example Usage in Relational Algebra

Consider a relation R(A, B) with attributes A and B. Let's illustrate the usage of these quantifiers:

- **Existential Quantifier:** ∃x (R(x, y) ∧ B(y) = 'value') selects tuples from R where there exists a tuple with B equal to 'value'.
- **Universal Quantifier:** ∀x (R(x, y) → A(y) > 10) selects tuples from R where for all tuples, the attribute A is greater than 10.
- **Cardinality Quantifiers:**
 - ⋎x (R(x, y) ∧ A(y) > 20) selects tuples from R where there exists a tuple with A greater than 20.
 - ⋊x (R(x, y) ∧ A(y) > 30) selects tuples from R where for all tuples, A is greater than 30.