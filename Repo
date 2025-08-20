import random

# Questions, options, and answers
questions = [
    {
        "question": "Which planet is known as the Red Planet?",
        "options": ["Earth", "Mars", "Jupiter", "Saturn"],
        "answer": "Mars"
    },
    {
        "question": "Who wrote the national anthem of India?",
        "options": ["Rabindranath Tagore", "Bankim Chandra Chatterjee", "Sarojini Naidu", "Subhash Chandra Bose"],
        "answer": "Rabindranath Tagore"
    },
    {
        "question": "What is the capital of Australia?",
        "options": ["Sydney", "Melbourne", "Canberra", "Perth"],
        "answer": "Canberra"
    },
    {
        "question": "Which gas do plants absorb from the atmosphere?",
        "options": ["Oxygen", "Nitrogen", "Carbon Dioxide", "Hydrogen"],
        "answer": "Carbon Dioxide"
    }
]

prizes = ["₹1,000", "₹5,000", "₹10,000", "₹50,000"]
lifeline_used = False

def use_5050(options, correct_answer):
    incorrect = [opt for opt in options if opt != correct_answer]
    removed = random.sample(incorrect, 2)
    return [opt for opt in options if opt not in removed]

print("🎉 Welcome to KBC - Kaun Banega Crorepati 🎉")
print("You have one lifeline: 50:50\n")

for i, q in enumerate(questions):
    print(f"\nQuestion {i+1} for {prizes[i]}:")
    print(q["question"])
    for idx, opt in enumerate(q["options"], start=1):
        print(f"{idx}. {opt}")

    if not lifeline_used:
        print("Type '5050' to use your lifeline.")

    user_input = input("Enter your answer (1-4) or '5050': ")

    if user_input == "5050" and not lifeline_used:
        lifeline_used = True
        reduced_options = use_5050(q["options"], q["answer"])
        print("\nLifeline activated! Here are your options:")
        for idx, opt in enumerate(reduced_options, start=1):
            print(f"{idx}. {opt}")
        user_input = input("Enter your answer (1-2): ")
        selected = reduced_options[int(user_input)-1]
    else:
        selected = q["options"][int(user_input)-1]

    if selected == q["answer"]:
        print(f"✅ Correct! You've won {prizes[i]}")
    else:
        print(f"❌ Wrong answer. The correct answer was: {q['answer']}")
        print("Game Over.")
        break
else:
    print("\n🎊 Congratulations! You've answered all questions correctly and won ₹50,000!")

