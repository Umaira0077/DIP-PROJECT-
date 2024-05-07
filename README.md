!pip install openCV-python
!pip install numpy
!pip install matplotlib
# import necessary library
import matplotlib.pyplot as plt
# for computer vision operations
import cv2 as cv
import cv2
[07/05, import random

# Define questions and options
questions = [
    {
        "question": "What is the capital of France?",
        "options": ["Paris", "London", "Berlin", "Rome"],   
    },
    {
        "question": "What is the largest mammal?",
        "options": ["Elephant", "Blue Whale", "Giraffe", "Lion"],       
    },
    {
        "question": "What is the chemical symbol for water?",
        "options": ["H2O", "O2", "CO2", "H2SO4"], 
    },
        {
        "question": "Which word is the synonym of big?",
        "options": ["Large", "Small", "Tiny", "Huge"],       
    },
    {
       "question": "Which word is the synonym of happy?",
        "options": ["Sad", "Joyful", "Angry", "Excited"],
    },
     {
       "question": "Which word is the homophone of pair?",
        "options": ["Pier", "Peer", "Pair", "Pare"], 
    },
     {
       "question": "Which word is the opposite of Bright?",
        "options": ["Dim", "Gloomy", "Light", "Dark"],        
    },
      {
       "question": "Which word is the synonym of cold?",
        "options": ["Cool", "Warm", "Chilled", "Hot"], 
    },
    {
       "question": "Which planet isknown as the Red Planet?",
        "options": ["Jupyter", "Earth", "Venus", "Mars"], 
    },
      {
       "question": "What is the chemical symbol of GOLD?",
        "options": ["Au", "Ag", "Fe", "Hg"], 
    },
]

# Shuffle the questions
random.shuffle(questions)

# Function to display questions
def display_questions(questions):
    for i, question in enumerate(questions, start=1):
        print(f"Question {i}: {question['question']}")
        for j, option in enumerate(question['options'], start=1):
            print(f"{chr(96+j)}. {option}")
        print()

# Display questions
display_questions(questions)
[07/05, 7def calculate_marks(student_responses, correct_answers):
    marks = {}
    for student, responses in student_responses.items():
        score = sum([1 for response, correct in zip(responses, correct_answers) if response == correct])
        marks[student] = score
    return marks

def calculate_percentage(marks, total_marks):
    percentages = {}
    for student, score in marks.items():
        percentage = (score / total_marks) * 100
        percentages[student] = percentage
    return percentages

# Example usage:
student_responses = {
    "Student1": ["A", "B", "C", "A", "D", "C", "C", "B", "A", "A"],
    "Student2": ["A", "B", "C", "A", "B", "A", "A", "A", "A", "A"],
    "Student3": ["A", "B", "C", "D", "A", "B", "A", "B", "B", "A"],
}

correct_answers = ["D", "B", "D", "A", "B", "C", "A", "A", "B", "A"]

total_marks = len(correct_answers)

# Calculate marks
marks = calculate_marks(student_responses, correct_answers)

# Calculate percentage
percentages = calculate_percentage(marks, total_marks)

# Display results
for student, score in marks.items():
    percentage = percentages[student]
    print(f"{student}: Marks - {score}/{total_marks}, Percentage - {percentage}%")
