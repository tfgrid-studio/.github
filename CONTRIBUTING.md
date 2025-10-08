# Contributing to TFGrid Compose

Thank you for your interest in contributing to TFGrid Compose! We welcome contributions from everyone.

## How to Contribute

### Reporting Issues

- Use the issue tracker in the relevant repository
- Describe the issue clearly
- Include steps to reproduce
- Provide system information if relevant

### Suggesting Features

- Open an issue with the `enhancement` label
- Describe the feature and its use case
- Explain why it would be valuable

### Contributing Code

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/my-feature
   ```
3. **Make your changes**
   - Follow existing code style
   - Add tests if applicable
   - Update documentation
4. **Commit your changes**
   ```bash
   git commit -m "Add feature: description"
   ```
5. **Push to your fork**
   ```bash
   git push origin feature/my-feature
   ```
6. **Open a Pull Request**
   - Describe your changes
   - Reference any related issues
   - Wait for review

## Development Setup

### Prerequisites

- Git
- Terraform
- Ansible
- Bash
- A ThreeFold Grid account (for testing)

### Clone and Setup

```bash
# Clone the repository
git clone https://github.com/tfgrid-compose/tfgrid-deployer
cd tfgrid-deployer

# Make CLI executable
chmod +x cli/tfgrid-compose

# Run help
./cli/tfgrid-compose help
```

## Code Style

### Shell Scripts

- Use `#!/usr/bin/env bash` shebang
- Set `set -e` for error handling
- Use meaningful variable names
- Add comments for complex logic
- Follow existing style

### YAML Files

- Use 2-space indentation
- Be consistent with formatting
- Add comments for clarity

### Documentation

- Use Markdown
- Keep it clear and concise
- Include examples
- Update when changing functionality

## Testing

### Manual Testing

```bash
# Test deployment
./cli/tfgrid-compose up ../tfgrid-ai-agent

# Test management commands
./cli/tfgrid-compose status tfgrid-ai-agent
./cli/tfgrid-compose logs tfgrid-ai-agent
./cli/tfgrid-compose ssh tfgrid-ai-agent

# Test destroy
./cli/tfgrid-compose down tfgrid-ai-agent
```

### Test Checklist

- [ ] Deployment works end-to-end
- [ ] All commands function correctly
- [ ] Error handling works properly
- [ ] State management is correct
- [ ] Cleanup works properly

## Documentation

When adding features, update:

- README.md
- Inline code comments
- User guides
- API documentation (if applicable)

## Pull Request Process

1. **Ensure tests pass** (when we have automated tests)
2. **Update documentation**
3. **Describe your changes clearly**
4. **Reference related issues**
5. **Wait for review** from maintainers
6. **Address feedback** if requested
7. **Celebrate!** 🎉 When merged

## What We're Looking For

### High Priority

- 🧪 **Testing** - Automated tests, test cases
- 📝 **Documentation** - Guides, examples, tutorials
- 🐛 **Bug Fixes** - Fix issues, improve stability
- 🎨 **Patterns** - New deployment patterns
- 📦 **Example Apps** - More reference applications

### Welcome Contributions

- Performance improvements
- Error handling enhancements
- User experience improvements
- Code refactoring
- Security improvements

## Community

- Be respectful and inclusive
- Follow our [Code of Conduct](./CODE_OF_CONDUCT.md)
- Help others in discussions
- Share your knowledge

## Questions?

- Open a discussion in the relevant repo
- Ask in issues (we don't bite!)
- Check existing documentation first

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Appreciated by the community! ❤️

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (Apache 2.0 for FOSS repositories).

---

**Thank you for contributing to TFGrid Compose!** 🚀
