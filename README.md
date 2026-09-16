# 🏥 Medigo

### AI-Assisted Doctor Appointment Booking Platform

Medigo is an AI-assisted healthcare platform that helps patients find suitable doctors and coordinate appointments through a conversational interface.

Instead of manually searching through doctors and medical specializations, users can describe their symptoms naturally. Medigo's AI pipeline analyzes the symptoms, identifies the relevant medical specialization, matches the patient with an available doctor, and helps coordinate an appointment.

---

## ✨ Features

- 🤖 **AI-Powered Symptom Analysis**
  - Understands symptoms described in natural language.
  - Identifies the relevant medical specialization.

- 👨‍⚕️ **Intelligent Doctor Matching**
  - Matches patients with suitable doctors based on analyzed symptoms.
  - Uses doctor availability and specialization data.

- 📅 **Appointment Coordination**
  - Helps coordinate available appointment time slots.

- 🔐 **User Authentication**
  - Secure signup and login.
  - JWT-based authentication.

- 📧 **Email OTP Verification**
  - Sends OTP verification emails during signup.
  - Activates the account after successful verification.

- 👤 **User Profile**
  - Profile management for patients.

- 💬 **Conversational AI Interface**
  - Patients can interact with the healthcare assistant through chat instead of filling multiple forms.

- 🗄️ **MongoDB Database**
  - Stores user, doctor and appointment information.

- 🔌 **Service-Based Architecture**
  - Frontend, backend and AI services are separated for independent development and scaling.

---

## 🧠 AI Agent Architecture

Medigo uses **three specialized AI agents** powered by Google Gemini through CrewAI:

```text
                 Patient
                    │
                    ▼
             💬 Chat Interface
                    │
                    ▼
          ┌───────────────────┐
          │   Backend API     │
          │   Node + Express  │
          └─────────┬─────────┘
                    │
                    ▼
          ┌───────────────────┐
          │   AI Agent Layer  │
          │ Python + FastAPI  │
          └─────────┬─────────┘
                    │
          ┌─────────┼─────────┐
          ▼         ▼         ▼
     🧠 Symptom   👨‍⚕️ Doctor   📅 Booking
       Analyzer     Matcher    Coordinator
          │         │         │
          └─────────┼─────────┘
                    ▼
              Google Gemini
                    │
                    ▼
                MongoDB
