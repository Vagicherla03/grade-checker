# deployment test
from flask import Flask, render_template_string

app = Flask(__name__)

def grade_checker(marks):
    if marks >= 90:
        return "A"
    elif marks >= 75:
        return "B"
    elif marks >= 50:
        return "C"
    else:
        return "Fail"

@app.route('/')
def show_grades():
    marks_list = {"Kowshik": 85, "Mani": 45}
    results = {student: grade_checker(marks) for student, marks in marks_list.items()}
    return render_template_string('''
        <h1>Student Grades</h1>
        <ul>
        {% for student, grade in results.items() %}
            <li>{{ student }}: {{ grade }}</li>
        {% endfor %}
        </ul>
    ''', results=results)

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
import os
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=int(os.environ.get("PORT", 8000)))

