# Quick Start Guide 🚀

**Ready to begin your ML/DL mastery journey? Start here!**

---

## Day 1: Setup & Orientation (Today!)

### Step 1: Environment Setup ⚙️

#### Install Python (if not already)
```powershell
# Check Python version (need 3.8+)
python --version

# If needed, install from python.org
```

#### Create Virtual Environment
```powershell
# Navigate to your learning folder
cd "c:\DL&ML learning"

# Create virtual environment
python -m venv venv

# Activate it
.\venv\Scripts\Activate

# Your prompt should now show (venv)
```

#### Install Essential Libraries
```powershell
# Create requirements.txt first
```

Create `requirements.txt`:
```txt
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
jupyter>=1.0.0
jupyterlab>=3.0.0
ipython>=7.0.0
```

```powershell
# Install packages
pip install -r requirements.txt

# Verify installation
python -c "import numpy; import pandas; print('Success!')"
```

#### Setup Jupyter
```powershell
# Install Jupyter extensions
jupyter labextension install @jupyter-widgets/jupyterlab-manager

# Launch Jupyter Lab
jupyter lab
```

### Step 2: Git Setup 🔧

```powershell
# Initialize Git repository
git init

# Check .gitignore exists
cat .gitignore

# First commit
git add .
git commit -m "Initial commit: Learning roadmap and structure"

# Create GitHub repository and push
# (Create repo on GitHub first, then:)
git remote add origin https://github.com/yourusername/DL-ML-Learning.git
git branch -M main
git push -u origin main
```

### Step 3: Familiarize with Roadmap 📖

1. **Read [ROADMAP.md](ROADMAP.md)** - Complete learning path
2. **Read [README.md](README.md)** - Repository overview
3. **Read [01-Foundations/README.md](01-Foundations/README.md)** - Where to start

### Step 4: First Learning Session 💡

Create your first notebook:

```powershell
# Navigate to foundations
cd "01-Foundations/Math/Linear-Algebra"

# Create a notebook (or use Jupyter Lab interface)
jupyter lab
```

Create `01-vectors-basics.ipynb`:

```python
# Cell 1: Imports
import numpy as np
import matplotlib.pyplot as plt

# Cell 2: Create vectors
v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

print(f"v1: {v1}")
print(f"v2: {v2}")

# Cell 3: Vector operations
print(f"v1 + v2 = {v1 + v2}")
print(f"v1 · v2 = {np.dot(v1, v2)}")  # Dot product

# Cell 4: Visualize (2D vectors)
v1_2d = np.array([3, 2])
v2_2d = np.array([1, 3])

plt.figure(figsize=(8, 6))
plt.quiver(0, 0, v1_2d[0], v1_2d[1], angles='xy', scale_units='xy', scale=1, color='r', label='v1')
plt.quiver(0, 0, v2_2d[0], v2_2d[1], angles='xy', scale_units='xy', scale=1, color='b', label='v2')
plt.xlim(-1, 5)
plt.ylim(-1, 5)
plt.grid()
plt.legend()
plt.title('Vector Visualization')
plt.show()
```

### Step 5: Update Progress 📝

Open [PROGRESS.md](PROGRESS.md) and log today's work:

```markdown
## Day 1 - March 7, 2026

### 📚 Theory Covered
- Read complete roadmap
- Understood learning structure
- Reviewed Phase 1 goals

### 💻 Implementation
- Set up Python environment
- Created first Jupyter notebook
- Practiced vector operations in NumPy

### 🎯 Achievements
- ✅ Environment setup complete
- ✅ Git repository initialized
- ✅ First code written

### 💡 Key Learnings
- NumPy makes vector operations easy
- Visualization helps understanding
- Importance of structured learning

### ⏭️ Tomorrow's Plan
- Continue with vectors (magnitude, unit vectors)
- Matrix operations
- Start calculus review
```

---

## Week 1 Plan: Linear Algebra 📐

### Day 1 (Today): Setup + Vectors Basics
- [x] Environment setup
- [x] Vector creation and operations
- [ ] Magnitude and normalization

### Day 2: Vectors Deep Dive
- [ ] Unit vectors
- [ ] Orthogonality
- [ ] Projections
- **Code:** Implement vector operations from scratch

### Day 3: Matrices Basics
- [ ] Matrix creation
- [ ] Matrix addition/multiplication
- [ ] Transpose
- **Code:** Implement matrix multiplication

### Day 4: Matrix Operations
- [ ] Identity matrix
- [ ] Inverse
- [ ] Determinant
- **Code:** Implement basic operations

### Day 5: Eigenvalues & Eigenvectors
- [ ] Concept and intuition
- [ ] Calculation
- [ ] Applications
- **Code:** Compute eigenvalues

### Day 6: Advanced Topics
- [ ] SVD (Singular Value Decomposition)
- [ ] Matrix factorization
- **Code:** Implement PCA basics

### Day 7: Review & Project
- [ ] Review all concepts
- [ ] Build mini-project: Image compression using SVD
- [ ] Update progress tracker

---

## Week 2 Plan: Calculus & Probability

### Calculus (Days 8-11)
- Derivatives
- Partial derivatives
- Chain rule
- Gradient descent implementation

### Probability (Days 12-14)
- Probability distributions
- Bayes theorem
- Statistical concepts
- Practical applications

---

## Daily Routine Template ⏰

### Morning (1 hour before work/study)
```
30 min: Read theory
- Book chapter or video lecture
- Take notes in LEARNING_NOTES.md

30 min: Quick coding practice
- Small implementation
- Algorithm problem
```

### Evening (2-3 hours)
```
1 hour: Deep implementation
- Algorithm from scratch
- Work on project

1 hour: Practice & experiments
- Test on datasets
- Visualizations
- Debugging

30 min: Documentation
- Update PROGRESS.md
- Write explanations
- Commit to Git
```

---

## Essential Commands Cheat Sheet 📋

### Python Virtual Environment
```powershell
# Activate
.\venv\Scripts\Activate

# Deactivate
deactivate

# Install package
pip install package-name

# Export requirements
pip freeze > requirements.txt
```

### Jupyter
```powershell
# Launch Lab
jupyter lab

# Launch Notebook
jupyter notebook

# Convert notebook to script
jupyter nbconvert --to script notebook.ipynb
```

### Git
```powershell
# Daily workflow
git add .
git commit -m "Day X: Completed topic Y"
git push

# Check status
git status

# View commit history
git log --oneline
```

### NumPy Quick Reference
```python
import numpy as np

# Create arrays
a = np.array([1, 2, 3])
b = np.zeros((3, 3))
c = np.ones((2, 2))
d = np.eye(3)  # Identity matrix

# Operations
np.dot(a, b)      # Dot product
np.matmul(A, B)   # Matrix multiplication
A.T               # Transpose
np.linalg.inv(A)  # Inverse
np.linalg.det(A)  # Determinant
```

---

## First Week Goals 🎯

By the end of week 1, you should:
- [ ] Have working Python environment
- [ ] Understand vector operations
- [ ] Comfortable with NumPy
- [ ] Implemented matrix operations from scratch
- [ ] Made 7 commits to GitHub
- [ ] Completed 1-2 notebooks
- [ ] Updated PROGRESS.md daily

---

## Common Issues & Solutions 🔧

### Issue: Python not found
```powershell
# Add Python to PATH or use full path
# Find Python location:
where python
```

### Issue: Package installation fails
```powershell
# Upgrade pip first
python -m pip install --upgrade pip

# Then install package
pip install package-name
```

### Issue: Jupyter kernel not found
```powershell
# Install ipykernel
pip install ipykernel

# Add environment to Jupyter
python -m ipykernel install --user --name=venv
```

### Issue: Import errors in notebook
```python
# Check you're using correct kernel
import sys
print(sys.executable)
# Should point to your venv
```

---

## Resources for Week 1 📚

### Videos
1. **3Blue1Brown - Essence of Linear Algebra** (YouTube)
   - Watch at least first 3 videos
   - Visual and intuitive

2. **Khan Academy - Linear Algebra**
   - Practice exercises
   - Step-by-step

### Reading
1. **"Mathematics for Machine Learning"** - Chapter 2
2. **NumPy Documentation** - Quickstart tutorial

### Practice
1. Implement all matrix operations from scratch
2. Visualize vector transformations
3. Solve 10 linear algebra problems

---

## Motivation & Tips 💪

### Stay Consistent
- Code daily, even if just 30 minutes
- Small progress > no progress
- Commit daily to maintain streak

### Don't Get Stuck
- If stuck for >30 min, ask for help or move on
- Google, Stack Overflow, ChatGPT are your friends
- Document what you couldn't solve

### Understand Deeply
- Don't just copy code
- Ask "why" for everything
- Implement from scratch before using libraries

### Track Everything
- Update PROGRESS.md daily
- Document in LEARNING_NOTES.md
- Commit to Git with meaningful messages

### Take Breaks
- Pomodoro technique (25 min work, 5 min break)
- Don't burn out
- This is a marathon, not a sprint

---

## Next Steps

1. ✅ Complete Day 1 tasks above
2. ✅ Set up development environment
3. ✅ Make first commit
4. 📅 Plan tomorrow's learning session
5. 🎯 Focus on Week 1: Linear Algebra

---

## Questions?

Document any questions in LEARNING_NOTES.md and research them. This is a self-guided journey - embrace the struggle and celebrate the victories!

---

**You're all set! Time to start learning. Remember: The journey of a thousand miles begins with a single step. You just took it! 🚀**

**Tomorrow:** Dive deep into vectors and matrices. See you then!
