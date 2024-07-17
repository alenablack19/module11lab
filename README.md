# module11lab
9.1 
grades_file = open('grades.txt', 'w')

while True:
    grade = input("Enter a grade (or 'q' to quit): ")
    if grade.lower() == 'q':
        break
    grades_file.write(grade + '\n')

grades_file.close()

9.2 
# Read grades from file
with open('grades.txt', 'r') as file:
    grades = [int(line.strip()) for line in file]

# Display individual grades
print("Individual Grades:", grades)

# Calculate total, count, and average
total = sum(grades)
count = len(grades)
average = total / count

# Display total, count, and average
print("Total:", total)
print("Count:", count)
print("Average:", average)

9.3
import csv

# Function to write student grades to a CSV file
def write_student_grades(first_name, last_name, exam_grades):
    with open('grades.csv', mode='a', newline='') as file:
        writer = csv.writer(file)
        writer.writerow([first_name, last_name] + exam_grades)

# Example usage
write_student_grades('John', 'Doe', [85, 90, 88])
write_student_grades('Alice', 'Smith', [78, 82, 80])

