class Student:
    def __init__(self, name, surname, gender):
        self.name = name
        self.surname = surname
        self.gender = gender
        self.finished_courses = []
        self.courses_in_progress = []
        self.grades = {}

    def rate_hw(self, student, course, grade):
        if isinstance(student, Student) and course in self.courses_in_progress and course in lecturer.courses_attached:
            if course in student.grades:
                student.grades[course] += [grade]
            else:
                student.grades[course] = [grade]
        else:
            return 'Ошибка'

    def add_courses(self, course_name):
        self.finished_courses.append(course_name)

    #не знаю, как выполнить расчет средней оценки с циклом по словарю. В лекции было сказано,
    # что нужно сложить все хначения и разделить на количество. Но не знаю, где их взять, в каком словаре.

    def __str__(self):
        res = f'Имя': {self.name}\n'Фамилия' = {self.surname}\n'Средняя оценка за лекции' = {self.average_grade}\n'Курсы в процессе изучения' = {self.courses_in_progress}\n'Завершенные курсы' = {self.finished_courses}
        return res

class Mentor:
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname
        self.courses_attached = []

class Lecturer(Mentor):
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname
        self.courses_attached = []
        self.grade = {}
    def average_grade(self):
    #не знаю, как выполнить расчет средней оценки с циклом по словарю. В лекции было сказано,
    # что нужно сложить все хначения и разделить на количество. Но не знаю, где их взять, в каком словаре.

    def __str__(self):
        res = f'Имя': {self.name}\n'Фамилия'= {self.surname}\n'Средняя оценка за лекции' = {self.average_grade}
        return res

class Reviewer(Mentor):
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname
        self.courses_attached = []
    def rate_hw(self, student, course, grade):
        if isinstance(student, Student) and course in self.courses_attached and course in student.courses_in_progress:
            if course in student.grades:
                student.grades[course] += [grade]
            else:
                student.grades[course] = [grade]
        else:
            return 'Ошибка'

    def __str__(self):
        res = f'Имя': {self.name}\n'Фамилия' = {self.surname}\n'Средняя оценка за лекции' = {self.average_grade}
        return res




best_student = Student('Ruoy', 'Eman', 'your_gender')
best_student.courses_in_progress += ['Python']

cool_mentor = Mentor('Some', 'Buddy')
cool_mentor.courses_attached += ['Python']

cool_mentor.rate_hw(best_student, 'Python', 10)
cool_mentor.rate_hw(best_student, 'Python', 10)
cool_mentor.rate_hw(best_student, 'Python', 10)

print(best_student.grades)
