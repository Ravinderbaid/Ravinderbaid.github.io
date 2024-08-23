---
layout: default
title: "Database date types and their sizes"
---

The size of each data type in a database can vary depending on the database system you're using (e.g., MySQL, PostgreSQL, SQL Server, etc.) and the specific data type definitions within that system. Below is a general overview of common data types and their sizes:

### 1. **Integer Types**

- **TINYINT**:
  - Size: 1 byte
  - Range: -128 to 127 (signed), 0 to 255 (unsigned)
- **SMALLINT**:
  - Size: 2 bytes
  - Range: -32,768 to 32,767 (signed), 0 to 65,535 (unsigned)
- **MEDIUMINT** (MySQL-specific):
  - Size: 3 bytes
  - Range: -8,388,608 to 8,388,607 (signed), 0 to 16,777,215 (unsigned)
- **INT / INTEGER**:
  - Size: 4 bytes
  - Range: -2,147,483,648 to 2,147,483,647 (signed), 0 to 4,294,967,295 (unsigned)
- **BIGINT**:
  - Size: 8 bytes
  - Range: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 (signed), 0 to 18,446,744,073,709,551,615 (unsigned)

### 2. **Floating-Point Types**

- **FLOAT**:
  - Size: 4 bytes
  - Precision: 6-7 decimal digits
- **DOUBLE**:
  - Size: 8 bytes
  - Precision: 15-16 decimal digits
- **REAL**:
  - Often an alias for FLOAT or DOUBLE depending on the database system.
  - Size: Depends on the specific implementation.

### 3. **Fixed-Point Types**

- **DECIMAL / NUMERIC**:
  - Size: Varies based on the precision and scale.
  - For example, DECIMAL(10,2) requires approximately 5 bytes.

### 4. **Character Types**

- **CHAR(n)**:
  - Size: n bytes (fixed-length)
- **VARCHAR(n)**:
  - Size: Varies based on the actual length of the stored string, plus 1 or 2 bytes for length information.
  - Example: If you store a string of length 10 in VARCHAR(255), the storage requirement is 10 bytes + 1 byte for length = 11 bytes.
- **TEXT**:
  - Size: Varies depending on the database system.
  - Typically larger, often stored in a different storage area with a reference in the main table.

### 5. **Binary Types**

- **BINARY(n)**:
  - Size: n bytes (fixed-length)
- **VARBINARY(n)**:
  - Size: Varies based on the actual length of the stored binary data, plus 1 or 2 bytes for length information.
- **BLOB**:
  - Size: Varies, depending on the database system.
  - Used for large binary objects, like images or files.

### 6. **Date and Time Types**

- **DATE**:
  - Size: 3 bytes
- **TIME**:
  - Size: 3 bytes
- **DATETIME**:
  - Size: 8 bytes
- **TIMESTAMP**:
  - Size: 4 bytes (in some systems, it might be 8 bytes)
- **YEAR** (MySQL-specific):
  - Size: 1 byte

### 7. **Boolean Type**

- **BOOLEAN / BOOL**:
  - Size: Typically 1 byte (often stored as TINYINT(1) in MySQL).

### 8. **Other Data Types**

- **ENUM** (MySQL-specific):
  - Size: 1 or 2 bytes, depending on the number of enumeration values.
- **SET** (MySQL-specific):
  - Size: 1, 2, 3, 4, or 8 bytes, depending on the number of set members.

### 9. **UUID**

- **UUID**:
  - Size: 16 bytes (128 bits)

### Notes:

- **Database Specifics**: The exact size can vary depending on the database system's internal representation and any additional overhead or optimizations.
- **Overhead**: Storage sizes mentioned above are for the data itself. Database systems may add additional overhead for indexing, record headers, and other metadata.
- **Nullability**: If a column allows `NULL`, some databases add additional storage (e.g., 1 byte) to store the NULL status.
