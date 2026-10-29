# Chapter 1
## 1.1 Input Output
### Output
```
msg <- "Hello Bru"
print(msg)
```
Assigning msg variable with string "Hello Bru" inside then printing it

### Input
- Single input
```
name <- readline("Insert your name: ")
print(name)
```
- Multiple Input
```
{name <- readline("Insert your name: ")
age <- readline("Inser your age: ")}
print(name)
print(age)
```
## 1.2 Vector
Data structure that hold **multiple** elements of the same **data types**
- c() - Combine Value
```
c(value1, value2, ...)

#Example:
x <- c(1,2,3)
print x

#Output:
[1] 10 20 30 40
------------------------
#Another example
a <- c(1, 2)
b <- c(3, 4)

c(a, b)

#Output:
[1] 1 2 3 4
```
- seq()
	- from and to
	- by
	- length.out
	- along.with
```
# Count by twos from 0 to 10
seq(from = 0, to = 10, by = 2)
# Output: [1]  0  2  4  6  8 10

# Count backward from 5 to 1
seq(from = 5, to = 1, by = -1)
# Output: [1] 5 4 3 2 1

# Generate 4 evenly spaced numbers between 0 and 20
seq(from = 0, to = 20, length.out = 4)
# Output: [1]  0.000000  6.666667 13.333333 20.000000

# Given a vector of length 3
my_vector <- c("apple", "banana", "cherry")

# Create a sequence matching its length
seq(from = 1, to = 10, along.with = my_vector)
# Output: [1]  1.0  5.5 10.0
```

Finding minimum and maximum value: `min() & max()`
Finding minimum and maximum loaciton : `which.min() & which.max()`

Checking class:
```
# Numeric vector
x <- c(10.5, 5.2, 8.0)
class(x) 
# Output: [1] "numeric"

# Character vector (text)
names <- c("Alice", "Bob")
class(names) 
# Output: [1] "character"

# Logical vector (TRUE/FALSE)
flag <- c(TRUE, FALSE, TRUE)
class(flag) 
# Output: [1] "logical"
```
Class Conversion:
```
# Create a number as a character string
num_str <- "123"
class(num_str) # Output: [1] "character"

# Convert it to numeric
num_val <- as.numeric(num_str)
class(num_val) 
# Output: [1] "numeric"
```
## 1.3 List
Creating List using list() inserted into variable **my_info <- list()**
Accessing:
- my_info$name   (using $ sign)
- `my_info[[1]]` (using matrix bracket)
```
# Create a list with a character, a number, a vector, and a boolean
my_info <- list(
  name = "Alice",
  age = 28,
  scores = c(92, 88, 95),
  is_employed = TRUE
)

# Access by name using $
my_info$name 
# Output: [1] "Alice"

# Access by index using double brackets
my_info[[3]] 
# Output: [1] 92 88 95

# Accessing a sub-list with single brackets
class(my_info[1])
# Output: [1] "list" (Notice it's still a list, not a character string)

# Add a new element to the list
my_info$city <- "Boston"

# Update an existing element
my_info$age <- 29

print(my_info$age)
# Output: [1] 29

class(my_info)
# Output: [1] "list"

is.list(my_info)
# Output: [1] TRUE
```

## 1.4 Factor
Represent categorical data
```
# A vector of shirt sizes
sizes <- c("Medium", "Large", "Small", "Medium", "Small")

# Convert to a factor
size_factor <- factor(sizes)

print(size_factor)
# Output: [1] Medium Large  Small  Medium Small 
# Levels: Large Medium Small   (Notice they are sorted alphabetically)

levels(size_factor) 
# Output: [1] "Large" "Medium" "Small"


# Create an ordered factor with a custom sequence
size_ordered <- factor(sizes, 
                       levels = c("Small", "Medium", "Large"), 
                       ordered = TRUE)

print(size_ordered)
# Output: [1] Medium Large  Small  Medium Small 
# Levels: Small < Medium < Large  (Notice the < sign showing order)


# Remap abbreviations (M, F) to full words (Male, Female)
gender_code <- c("M", "F", "F", "M")

gender_factor <- factor(gender_code, 
                        levels = c("M", "F"), 
                        labels = c("Male", "Female"))

print(gender_factor)
# Output: [1] Male   Female Female Male  
# Levels: Male Female
```

## 1.5 Matrix
matrix(size(1:6), numberOfRow(nrow=2), numberOfCollumn(ncol=3), byrow = TRUE/FALSE)
```
# Create a matrix with numbers 1 through 6, spread across 2 rows and 3 columns
my_matrix <- matrix(1:6, nrow = 2, ncol = 3)

print(my_matrix)
# Output:
#      [,1] [,2] [,3]
# [1,]    1    3    5
# [2,]    2    4    6


# Fill row-by-row
my_matrix_row <- matrix(1:6, nrow = 2, ncol = 3, byrow = TRUE)

print(my_matrix_row)
# Output:
#      [,1] [,2] [,3]
# [1,]    1    2    3
# [2,]    4    5    6



# Element in row 1, column 2
my_matrix[1, 2]
# Output: [1] 3

# Entire first row
my_matrix[1, ]
# Output: [1] 1 3 5

# Entire second column
my_matrix[, 2]
# Output: [1] 3 4



# Create a matrix
scores <- matrix(c(90, 85, 88, 92), nrow = 2, ncol = 2)

# Assign names
rownames(scores) <- c("Alice", "Bob")
colnames(scores) <- c("Math", "Science")

print(scores)
# Output:
#       Math Science
# Alice   90      88
# Bob     85      92
```
