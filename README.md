# Growth-mindset-challenge-
Growth mindset challenge 
import streamlit as st
import random
import datetime

# Growth mindset quotes
quotes = [
    "Failure is an opportunity to grow.",
    "I can learn anything I want to.",
    "Challenges help me become stronger.",
    "Effort and attitude determine my abilities.",
    "Feedback is constructive, not personal.",
    "I am constantly improving through practice.",
    "I embrace challenges as a path to mastery."
]

# Growth mindset challenges
challenges = [
    "Write down one thing you struggled with today and how you overcame it.",
    "Try learning a new skill for 10 minutes.",
    "Give yourself positive self-talk in front of a mirror.",
    "Ask someone for feedback and use it to improve.",
    "Step out of your comfort zone—try something unfamiliar!",
    "Turn a mistake into a learning opportunity.",
    "Set a small goal and accomplish it today."
]

# Get today's date
today = datetime.date.today()

# App layout
st.title("🌱 Growth Mindset Challenge")
st.subheader(f"📅 Today's Date: {today}")

# Random quote
st.markdown("### 💡 Growth Mindset Quote:")
st.info(random.choice(quotes))

# Daily Challenge
st.markdown("### 🎯 Your Challenge for Today:")
challenge = random.choice(challenges)
st.success(challenge)

# Progress tracking
st.markdown("### ✅ Track Your Progress")
if "completed_challenges" not in st.session_state:
    st.session_state["completed_challenges"] = []

if st.button("Mark as Completed"):
    st.session_state["completed_challenges"].append((today, challenge))
    st.success("Challenge marked as completed!")

# Show past completed challenges
if st.session_state["completed_challenges"]:
    st.markdown("### 📜 Completed Challenges")
    for date, challenge in st.session_state["completed_challenges"]:
        st.write(f"**{date}:** {challenge}")

# Footer
st.markdown("---")
st.markdown("💪 Keep growing, keep learning!")

