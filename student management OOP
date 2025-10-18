class StudentDatabase:
    student_list = []
    def add_student(self,s):
        self.student_list.append(s)

    def find_student_by_id(self, student_id):
        for student in self.student_list:
            if student._student_id == student_id:
                return student
        return None

    def view_all_students(self):
        if not self.student_list:
            print("No students found.\n")
        else:
            for x in self.student_list:
                x.view_student_info()


class Student:
    def __init__(self, student_id, name, department, is_enrolled=False):
        self._student_id = student_id
        self._name = name
        self._department = department
        self._is_enrolled = is_enrolled

    def enroll_student(self):
        if self._is_enrolled:
            print(f"Student {self._student_id} already enrolled..")
        else:
            self._is_enrolled = True
            print(f"Student {self._student_id} enrolled successfully...")
            
    def drop_student(self):
        if not self._is_enrolled:
            print(f"Student {self._student_id} is not enrolled.")
        else:
            self._is_enrolled = False
            print(f"Student {self._student_id} has been dropped..")

    def view_student_info(self):
        print(f"ID: {self._student_id}",end=", ")
        print(f"Name: {self._name}",end=", ")
        print(f"Department: {self._department}",end=", ")
        print(f"Status: {self._is_enrolled}")



std = StudentDatabase()

s1 = Student("S101", "Hero alom", "Computer Science", True)
s2 = Student("S102", "Selim vai", "Math")
s3 = Student("S103", "AD Paul", "Physics", True)

std.add_student(s1)
std.add_student(s2)
std.add_student(s3)

def menu():
    while True:
        print("\n----- Student Management Manue -----")
        print("1. View All Students")
        print("2. Enroll Student")
        print("3. Drop Student")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            std.view_all_students()

        elif choice == '2':
            try:
                student_id = input("Enter student ID to enroll: ")
                student = std.find_student_by_id(student_id)
                if student:
                    student.enroll_student()
                else:
                    print("Error: Invalid student ID.\n")
            except ValueError:
                print("Error: Please enter a valid number.\n")

        elif choice == '3':
            try:
                student_id = input("Enter student ID to drop: ")
                student = std.find_student_by_id(student_id)
                if student:
                    student.drop_student()
                else:
                    print("Error: Invalid student ID.\n")
            except ValueError:
                print("Error: Please enter a valid number.\n")

        elif choice == '4':
            print("Exiting the system.....")
            break

        else:
            print("Invalid choice. Please enter a number between 1 and 4.\n")


menu()
