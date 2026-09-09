# Personal Study & Internship Planner Agent

A simple Python-based personal agent that helps organize study and internship tasks by priority and recommends what to work on first.

## What It Does

The Personal Study & Internship Planner Agent takes structured tasks from a JSON file and recommends which task should be worked on first.

It is designed for students and interns who have multiple assignments or study tasks and need a simple way to decide what to focus on.

The current version uses task priority (High, Medium, Low) to create a clear order.

## Who It Is For

- B.Tech / Computer Science students
- Students managing multiple assignments
- Interns balancing internship and study tasks
- Anyone who wants a simple task-prioritization tool

## Project Structure

- `agent.py` – contains the Python agent logic.
- `task.json` – contains the structured study/internship tasks.
- `build_log.md` – records the development iterations and testing.
- `README.md` – explains the project and how to use it.

## Requirements

- Python 3
- No external Python packages are required for the current version.

## Setup

Clone the repository:

    git clone https://github.com/vangaricharmi-cmyk/personal-study-agent.git

Open the project folder:

    cd personal-study-agent

Check that Python 3 is installed:

    python --version

## Usage

Run the agent with:

    python agent.py

The program asks what the user wants help with and then uses the tasks stored in `task.json` to recommend what should be studied first.

Example request:

    What should I study first?

The agent recommends the highest-priority pending task.

## Simple Architecture

    User Request
          |
          v
      agent.py
          |
          v
       task.json
          |
          v
     Read and sort tasks
       by priority
          |
          v
    High → Medium → Low
          |
          v
     Recommendation

## Data Flow

1. The user enters a request.
2. `agent.py` loads the structured tasks from `task.json`.
3. The agent reads the priority of each task.
4. Tasks are sorted using the priority order.
5. The highest-priority pending task is recommended first.
6. The recommendation is displayed to the user.

## Design Decision

I chose a scripted Python agent for the first version because it gives me direct control over the prioritization logic and makes the behavior easy to test.

Instead of building a more complicated workflow with integrations, I focused first on making the core prioritization behavior understandable and testable.

## Evaluation Results

The current implementation was tested with multiple study tasks having different priorities.

The agent correctly places High-priority work before Medium and Low priority work.

For the test request:

    What should I study first?

the agent recommended the High-priority Operating Systems task.

Result: PASS

The current evaluation demonstrates priority-based task ordering and recommendation.

## Limitations

The current version has some limitations:

- It mainly uses task priority for ordering.
- It does not yet automatically connect to a calendar.
- It does not automatically read assignments from external systems.
- Deadline conflicts are not automatically resolved.
- Large tasks are not automatically divided into work sessions.
- Dependencies and blockers are not fully handled.
- Task information is currently provided manually through the JSON file.

These limitations are intentional for the first working version. The goal was to prove the core prioritization behavior before adding more complex integrations.

## What I Would Build Next

For a future version, I would add:

1. Deadline-aware prioritization.
2. Workload estimation.
3. Dependency and blocker detection.
4. Automatic task breakdown.
5. Calendar and task integrations.
6. A more interactive interface.

## AI Transparency

AI was used during development to help with planning, reasoning about the agent design, and improving the implementation. I checked the project behavior myself by running and testing the agent rather than treating AI-generated suggestions as proof that the system worked.

## Repository

GitHub repository:

https://github.com/vangaricharmi-cmyk/personal-study-agent
