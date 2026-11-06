# Contributing to Voice Alert System

Thank you for your interest in contributing to Voice Alert System! We welcome all contributions, including bug fixes, documentation improvements, feature requests, and code enhancements.

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please treat all contributors and users with respect.

## Getting Started

### 1. Prerequisites
- **Python**: 3.10 or higher.
- **Microphone**: Working audio input device.
- **PortAudio**: Ensure PortAudio development libraries are available if building PyAudio from source.

### 2. Fork and Clone
```bash
git clone https://github.com/<your-username>/voice_check.git
cd voice_check
```

### 3. Set Up Development Environment
Create and activate a virtual environment:
```bash
python -m venv venv

# On Linux/macOS:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

Install runtime and development dependencies:
```bash
pip install --upgrade pip
pip install -r requirements.txt
pip install ruff black mypy
```

## Development Workflow

1. **Create a Feature Branch**:
   Always branch off `main` with a clear, descriptive name:
   ```bash
   git checkout -b feat/add-audio-device-selector
   # or
   git checkout -b fix/mask-log-credentials
   ```

2. **Code Style & Quality**:
   - Follow standard **PEP 8** guidelines.
   - Use `black` and `ruff` to format and lint your changes before committing:
     ```bash
     black .
     ruff check .
     ```

3. **Commit Messages**:
   We strictly follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:
   - `feat:` A new feature or capability.
   - `fix:` A bug fix.
   - `docs:` Documentation-only changes.
   - `refactor:` Code refactoring without functionality changes.
   - `test:` Adding or updating tests.
   - `ci:` Changes to CI/CD workflows and scripts.
   - `chore:` Maintenance tasks, dependency bumps, or build configuration.

   *Example*: `feat(audio): add input device enumeration dropdown`

## Submitting a Pull Request

1. Push your branch to your GitHub fork:
   ```bash
   git push origin <your-branch-name>
   ```
2. Open a Pull Request against the `main` branch of this repository.
3. Fill out the [Pull Request Template](PULL_REQUEST_TEMPLATE.md) completely, including details on how your changes were verified.
4. Ensure all continuous integration checks pass.
