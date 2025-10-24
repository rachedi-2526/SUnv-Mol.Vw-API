# Contributing to SUnv-Mol.Vw API

Thank you for your interest in contributing to SUnv-Mol.Vw API! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

### **Reporting Bugs**
- Use the [GitHub Issues](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues) page
- Include detailed steps to reproduce the bug
- Specify browser and operating system
- Include error messages or screenshots if applicable

### **Suggesting Features**
- Use the [GitHub Issues](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues) page
- Clearly describe the proposed feature
- Explain the use case and benefits
- Consider implementation complexity

### **Code Contributions**
1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

## 🛠️ Development Setup

### **Prerequisites**
- Modern web browser with WebGL support
- Git
- Node.js (optional, for development server)

### **Local Development**
```bash
# Clone your fork
git clone https://github.com/rachedi-2526/SUnv-Mol.Vw-API.git
cd SUnv-Mol.Vw-API

# Start development server
npm start
# or
python -m http.server 8000
# or
npx serve .
```

### **Testing**
- Test on multiple browsers (Chrome, Firefox, Safari, Edge)
- Test on different devices (desktop, tablet, mobile)
- Verify WebGL compatibility
- Test with various structure types (PDB, AlphaFold)

## 📝 Code Style Guidelines

### **HTML**
- Use semantic HTML5 elements
- Include proper accessibility attributes
- Maintain consistent indentation (2 spaces)

### **CSS**
- Use meaningful class names
- Follow BEM methodology when appropriate
- Include comments for complex styles
- Use CSS Grid and Flexbox for layouts

### **JavaScript**
- Use modern ES6+ features
- Include JSDoc comments for functions
- Use meaningful variable and function names
- Handle errors gracefully

### **General**
- Write clear, self-documenting code
- Include comments for complex logic
- Follow existing code patterns
- Test thoroughly before submitting

## 🧪 Testing Guidelines

### **Manual Testing**
- Test all visualization modes (Cartoon, Stick, Line, Sphere, Surface)
- Test all color schemes (Secondary Structure, Element, Chain, pLDDT)
- Test chain management for multi-chain structures
- Test atom picking functionality
- Test responsive design on different screen sizes

### **Test Structures**
Use these structures for testing:
- **Small**: 1CRN (46 residues)
- **Medium**: 4DFR (multi-chain)
- **Large**: 1ATJ (multi-chain)
- **AlphaFold**: AF-Q9I4X8-F1
- **Membrane**: 2POR

### **Browser Testing**
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 📋 Pull Request Guidelines

### **Before Submitting**
- [ ] Code follows style guidelines
- [ ] All tests pass
- [ ] Documentation updated if needed
- [ ] No console errors
- [ ] Cross-browser compatibility verified

### **Pull Request Template**
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## Testing
- [ ] Tested on multiple browsers
- [ ] Tested on different devices
- [ ] No console errors
- [ ] All existing functionality works

## Screenshots (if applicable)
Add screenshots to help explain your changes

## Additional Notes
Any additional information about the changes
```

## 🏷️ Issue Labels

We use the following labels for issues:
- `bug` - Something isn't working
- `enhancement` - New feature or request
- `documentation` - Improvements to documentation
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention is needed
- `question` - Further information is requested

## 📚 Documentation

### **Code Documentation**
- Include JSDoc comments for functions
- Document complex algorithms
- Explain non-obvious code sections

### **User Documentation**
- Update README.md for new features
- Add examples for new functionality
- Update demo page if needed

## 🎯 Roadmap

### **Short Term**
- Performance optimizations
- Additional color schemes
- Enhanced mobile support
- More surface rendering options

### **Long Term**
- Plugin system
- Custom shader support
- Collaborative features
- Advanced analysis tools

## 📞 Getting Help

- **GitHub Issues**: [Create an issue](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/issues)
- **Email**: [bioinformatics@univ-saida.dz](mailto:bioinformatics@univ-saida.dz)
- **Documentation**: [Wiki](https://github.com/rachedi-2526/SUnv-Mol.Vw-API/wiki)

## 🙏 Recognition

Contributors will be recognized in:
- README.md contributors section
- Release notes
- Academic publications (if applicable)

## 📄 License

By contributing to SUnv-Mol.Vw API, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to SUnv-Mol.Vw API! 🧬✨
