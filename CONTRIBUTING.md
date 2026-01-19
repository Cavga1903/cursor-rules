# Contributing to Cursor Rules

Thank you for your interest in contributing to Cursor Rules! This document provides guidelines and instructions for contributing.

## 🤝 How to Contribute

### Reporting Issues

If you find a bug or have a suggestion, please open an issue on GitHub:

1. Check if the issue already exists
2. If not, create a new issue with:
   - Clear title
   - Description of the problem or suggestion
   - Steps to reproduce (if applicable)
   - Expected vs actual behavior

### Submitting Changes

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the existing code style
   - Update CHANGELOG.md if needed
   - Update VERSION if it's a major change

4. **Test your changes**
   - Ensure all .mdc files have proper frontmatter
   - Check that symlinks work correctly
   - Verify documentation is up to date

5. **Commit your changes**
   ```bash
   git commit -m "feat: add your feature description"
   ```
   
   Use conventional commits:
   - `feat:` - New feature
   - `fix:` - Bug fix
   - `docs:` - Documentation changes
   - `refactor:` - Code refactoring
   - `chore:` - Maintenance tasks

6. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Create a Pull Request**
   - Provide a clear description
   - Reference related issues
   - Wait for review

## 📝 Code Style Guidelines

### Rule Files (.mdc)

- Always include frontmatter:
  ```markdown
  ---
  alwaysApply: true  # or false
  ---
  ```

- Use clear headings and structure
- Include examples (good/bad patterns)
- Add references to external resources
- Keep files under 500 lines when possible

### Documentation

- Use clear, concise language
- Include code examples
- Add links to relevant resources
- Keep README.md up to date

## 🎯 Areas for Contribution

### New Rules

- React/Next.js best practices
- TypeScript patterns
- Testing guidelines
- Security practices
- Performance optimization

### Improvements

- Better documentation
- More examples
- Template files for new projects
- CI/CD improvements
- Better integration guides

## 📋 Checklist for Contributors

Before submitting a PR, make sure:

- [ ] Code follows existing style
- [ ] Documentation is updated
- [ ] CHANGELOG.md is updated (if needed)
- [ ] VERSION is updated (if major change)
- [ ] All files have proper frontmatter
- [ ] No symlinks are broken
- [ ] README.md is accurate

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/cursor-rules.git
   cd cursor-rules
   ```

2. Create a branch:
   ```bash
   git checkout -b feature/your-feature
   ```

3. Make your changes

4. Test locally:
   ```bash
   # Check file structure
   test -f README.md && echo "✅ README.md exists"
   
   # Validate .mdc files
   for file in *.mdc; do
     head -1 "$file" | grep -q "^---$" && echo "✅ $file has frontmatter"
   done
   ```

5. Commit and push

## 📧 Questions?

If you have questions, feel free to:
- Open an issue
- Start a discussion
- Contact maintainers

Thank you for contributing! 🎉

---

**Last Updated:** 2026-01-19
