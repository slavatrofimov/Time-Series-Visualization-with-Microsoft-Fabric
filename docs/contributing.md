# Contributing

Thank you for your interest in contributing to the Time Series Visualization solution! This document provides guidelines for contributing to this project.

## Ways to Contribute

### Reporting Issues

Found a bug or have a suggestion? Please open an issue on GitHub:

1. Check if a similar issue already exists
2. Use a clear, descriptive title
3. Provide detailed information:
    - Steps to reproduce (for bugs)
    - Expected vs. actual behavior
    - Screenshots if applicable
    - Your environment (Power BI version, browser, etc.)

### Suggesting Enhancements

We welcome ideas for improvements:

- New features or capabilities
- Documentation improvements
- User experience enhancements
- Performance optimizations

### Code Contributions

#### Before You Start

1. **Check existing issues** to see if someone is already working on it
2. **Open an issue** to discuss significant changes before starting work
3. **Fork the repository** and create a branch for your changes

#### Development Setup

1. Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/Time-Series-Visualization-with-Microsoft-Fabric.git
   ```

2. Install Power BI Desktop (latest version)

3. Open the relevant `.pbip` file to make changes

#### Making Changes

1. Create a descriptive branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Make your changes following the coding guidelines below

3. Test your changes thoroughly

4. Commit with clear messages:
   ```bash
   git commit -m "Add feature: description of what you added"
   ```

#### Submitting a Pull Request

1. Push your changes to your fork
2. Open a Pull Request against the `main` branch
3. Fill out the PR template with:
    - Description of changes
    - Related issue numbers
    - Testing performed
    - Screenshots if applicable

## Coding Guidelines

### Power Query (M Language)

- Use descriptive variable names
- Add comments for complex logic
- Follow consistent formatting
- Handle errors gracefully

### KQL Queries

- Use meaningful table and column aliases
- Add comments for complex query sections
- Optimize for performance
- Test with realistic data volumes

### Power BI Reports

- Use consistent naming conventions for:
    - Pages
    - Visuals
    - Measures
    - Parameters
- Document any custom calculations
- Ensure accessibility (colors, contrast, alt text)

### Documentation

- Use clear, concise language
- Include examples where helpful
- Keep formatting consistent with existing docs
- Update relevant sections when making code changes

## Documentation Contributions

Documentation is crucial! Ways to help:

- Fix typos or unclear explanations
- Add examples or use cases
- Improve getting started guides
- Translate to other languages

### Local Documentation Preview

To preview documentation changes locally:

```bash
# Install MkDocs
pip install mkdocs-material

# Serve locally
mkdocs serve
```

Then open `http://localhost:8000` in your browser.

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors.

### Expected Behavior

- Be respectful and considerate
- Welcome newcomers and help them get started
- Accept constructive criticism gracefully
- Focus on what's best for the community

### Unacceptable Behavior

- Harassment or discriminatory language
- Personal attacks or trolling
- Publishing others' private information
- Other conduct inappropriate in a professional setting

## Getting Help

- **Questions about the project**: Open a Discussion on GitHub
- **Bug reports**: Open an Issue on GitHub
- **Security concerns**: Please report privately via GitHub Security Advisories

## Recognition

Contributors will be recognized in:

- The project README
- Release notes for significant contributions
- Our documentation

Thank you for helping improve this project! 🙏
