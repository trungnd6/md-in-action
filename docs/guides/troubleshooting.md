# Troubleshooting Common Markdown Issues

Having trouble with your Markdown? This guide covers the most common problems and their solutions.

## Table of Contents
- [Formatting Issues](#formatting-issues)
- [Link Problems](#link-problems)
- [Image Display Issues](#image-display-issues)
- [Code Block Problems](#code-block-problems)
- [Platform-Specific Issues](#platform-specific-issues)
- [Preview and Rendering Issues](#preview-and-rendering-issues)

---

## Formatting Issues

### Headers Not Rendering

**Problem**: Headers appear as plain text
```markdown
#This doesn't work
##Neither does this
```

**Solution**: Add a space after the `#`
```markdown
# This works correctly
## So does this
```

### Lists Not Formatting Properly

**Problem**: List items appear as plain text
```markdown
-Item 1
-Item 2
*Item 3
```

**Solution**: Add spaces after list markers and use consistent markers
```markdown
- Item 1
- Item 2
- Item 3
```

**Problem**: Nested lists not indenting
```markdown
- Main item
- Nested item (wrong)
```

**Solution**: Use proper indentation (2 or 4 spaces)
```markdown
- Main item
  - Nested item (correct)
    - More nested
```

### Bold and Italic Not Working

**Problem**: Asterisks showing instead of formatting
```markdown
This text has *spaces * around asterisks
**This has spaces ** too
```

**Solution**: No spaces inside the markers
```markdown
This text is *properly formatted*
**This is bold correctly**
```

### Mixed Formatting Issues
**Problem**: Inconsistent results across platforms
```markdown
**Bold _and italic_** (mixed markers)
```

**Solution**: Use consistent markers
```markdown
**Bold *and italic*** (consistent)
***Bold and italic*** (alternative)
```

---

## Link Problems

### Broken Internal Links

**Problem**: Links to other files don't work
```markdown
[Guide](wrong-path.md)
[API Docs](api.md) # file is in subdirectory
```

**Solution**: Use correct relative paths
```markdown
[Guide](correct-path.md)
[API Docs](docs/api.md)
[Parent Directory](../README.md)
```

### Link Text Not Displaying

**Problem**: URL shows instead of link text
```markdown
[https://example.com](https://example.com)
```

**Solution**: Use descriptive link text
```markdown
[Visit Example Website](https://example.com)
```

### Reference Links Not Working

**Problem**: Reference links showing as plain text
```markdown
This is a [reference link][1] that doesn't work.
```

**Solution**: Add the reference definition
```markdown
This is a [reference link][1] that works.

[1]: https://example.com "Reference Link Title"
```

### Anchor Links Not Working

**Problem**: Links to page sections don't work
```markdown
[Go to section](#My Section) # spaces and capitals
```

**Solution**: Use proper anchor format
```markdown
[Go to section](#my-section) # lowercase with hyphens
```

---

## Image Display Issues

### Images Not Showing

**Problem**: Image syntax incorrect
```markdown
[Image](image.jpg) # This is a link, not an image
```

**Solution**: Use exclamation mark for images
```markdown
![Image Description](image.jpg)
```

### Broken Image Paths

**Problem**: Wrong file paths
```markdown
![Logo](logo.png) # file is in images folder
```

**Solution**: Use correct relative paths
```markdown
![Logo](./images/logo.png)
![Logo](images/logo.png)
```

### Images Too Large

**Problem**: Images display at full size
```markdown
![Huge Image](large-image.jpg)
```

**Solutions**: 
1. **HTML approach** (when supported):
```html
<img src="large-image.jpg" alt="Resized Image" width="300">
```

2. **CSS approach** (with style support):
```markdown
![Resized Image](large-image.jpg){: width="300px"}
```

3. **Pre-resize the image** (recommended)

---

## Code Block Problems

### Code Not Highlighting

**Problem**: No syntax highlighting
````markdown
```
function example() {
    return "no highlighting";
}
```
````

**Solution**: Specify the language
````markdown
```javascript
function example() {
    return "with highlighting";
}
```
````

### Code Block Not Rendering

**Problem**: Backticks showing as text
```markdown
```javascript
code here
``` # not enough backticks or wrong placement
```

**Solution**: Use proper fencing
````markdown
```javascript
code here
```
````

**Alternative**: Use indentation (4 spaces)
```markdown
    function example() {
        return "indented code block";
    }
```

### Inline Code Issues

**Problem**: Backticks not working
```markdown
Use the `git commit` command. # smart quotes
```

**Solution**: Use straight backticks
```markdown
Use the `git commit` command.
```

---

## Platform-Specific Issues

### GitHub Issues

**Problem**: Task lists not working
```markdown
- [x] Done
- [ ] Todo # wrong bracket type
```

**Solution**: Use square brackets
```markdown
- [x] Done  
- [ ] Todo
```

**Problem**: Tables not aligning
```markdown
|Name|Age|City| # no spaces
|---|---|---|
|John|25|NYC|
```

**Solution**: Add proper spacing
```markdown
| Name | Age | City |
|------|-----|------|
| John | 25  | NYC  |
```

### Obsidian Issues

**Problem**: Internal links not working
```markdown
[Link](Other Note.md) # wrong format for Obsidian
```

**Solution**: Use double brackets
```markdown
[[Other Note]]
```

### Jekyll/Hugo Issues

**Problem**: Front matter causing errors
```markdown
# My Post # missing front matter
Content here
```

**Solution**: Add proper front matter
```markdown
---
title: "My Post"
date: 2024-10-23
---

# My Post
Content here
```

---

## Preview and Rendering Issues

### Different Rendering Across Platforms

**Problem**: Markdown looks different on different platforms

**Solutions**:
1. **Stick to basic syntax** for maximum compatibility
2. **Test on target platform** when possible
3. **Use CommonMark standard** features
4. **Avoid platform-specific extensions** when sharing across platforms

### Preview Not Updating

**Problem**: Changes not showing in preview

**Solutions**:
1. **Refresh the preview** manually
2. **Save the file** first
3. **Check if auto-refresh is enabled**
4. **Restart the application**

### Garbled Characters

**Problem**: Special characters showing as symbols

**Solutions**:
1. **Check file encoding** (should be UTF-8)
2. **Save with UTF-8 encoding**
3. **Use HTML entities** for special characters:
   - `&amp;` for &
   - `&lt;` for <
   - `&gt;` for >

---

## General Debugging Tips

### Check Your Syntax
1. **Look for typos** in Markdown syntax
2. **Check spacing** around formatting markers
3. **Verify file extensions** (.md, .markdown)
4. **Use consistent formatting** throughout

### Test Incrementally
1. **Start simple** and add complexity gradually
2. **Test each section** individually
3. **Copy working examples** and modify them
4. **Use online validators** when available

### Common Gotchas
- **Smart quotes** (`"` instead of `"`) break links
- **No blank lines** between sections can cause issues
- **Mixing tabs and spaces** for indentation
- **Wrong file encoding** (use UTF-8)
- **Missing file extensions** in links

### Validation Tools
```bash
# Install markdown linter
npm install -g markdownlint-cli

# Check your files
markdownlint *.md

# Install link checker  
npm install -g markdown-link-check

# Verify links
markdown-link-check README.md
```

---

## Still Having Problems?

### Quick Checklist
- [ ] Are you using the correct Markdown syntax?
- [ ] Do you have proper spacing around formatting?
- [ ] Are file paths correct and files exist?
- [ ] Is your file saved with UTF-8 encoding?
- [ ] Are you testing on the right platform?

### Get Help
- 🔍 Search existing [GitHub Issues](https://github.com/trungnd6/md-in-action/issues)
- 💬 Ask a question in [Discussions](https://github.com/trungnd6/md-in-action/discussions)  
- 📖 Check platform-specific documentation
- 🌐 Try online Markdown editors for testing

### Report a Bug
If you found a real issue with this guide:
1. Check if it's already reported
2. Create a [new issue](https://github.com/trungnd6/md-in-action/issues/new)
3. Include:
   - What you expected
   - What actually happened  
   - Steps to reproduce
   - Platform/editor you're using

---

## Related Documents
- [Getting Started Guide](getting-started.md)
- [Complete Syntax Reference](../README.md#universal-markdown-syntax)
- [Platform-Specific Guides](../platforms/)
- [Contributing Guidelines](../CONTRIBUTING.md)

*Last updated: October 23, 2024*