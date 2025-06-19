# Agentic Coding Best Practices with Claude Code

*Reference: https://www.anthropic.com/engineering/claude-code-best-practices*

## Setup and Configuration

### CLAUDE.md Files
Create `CLAUDE.md` files in your repositories to:
- Document bash commands and development scripts
- Define code style guidelines and conventions
- Outline repository etiquette and workflow rules
- Capture developer environment details and setup instructions

### Tool Permissions Management
- Use `/permissions` command to manage allowed tools
- Carefully control system modification capabilities
- Consider using `.claude/settings.json` for persistent configurations
- Grant specific permissions like `mcp__puppeteer__*` for browser automation

## Development Workflows

### Explore-Plan-Code-Commit Approach
1. **Explore**: Read relevant files first to understand the codebase
2. **Plan**: Have Claude create a detailed implementation plan
3. **Think**: Use "think" modes for deeper analysis of complex problems
4. **Code**: Implement solution incrementally with clear steps
5. **Commit**: Commit with clear explanations of changes and rationale

### Test-Driven Development
1. Write tests first before implementation
2. Confirm tests initially fail (red phase)
3. Implement code to pass tests (green phase)
4. Verify implementation isn't overfitting to specific test cases
5. Refactor and improve code quality

### Visual Iteration Techniques
- Use screenshots for visual feedback during UI development
- Provide design mockups and specifications
- Iterate 2-3 times for significantly improved results
- Give Claude visual tools to see outputs for best results

## Advanced Techniques

### Multi-Claude Workflows
- Use separate Claude instances for writing vs reviewing code
- Leverage git worktrees for parallel development tasks
- Implement peer review processes with different Claude sessions

### Automation and Headless Mode
- Use headless mode (`-p flag`) for CI/infrastructure tasks
- Create custom slash commands for repeated workflows
- Implement issue triage and automated debugging scripts
- Use `--output-format stream-json` for streaming JSON output

### MCP Integration
- Install and configure MCP servers for extended capabilities
- Use Puppeteer MCP for browser automation and visual testing
- Enable screenshot-driven development workflows
- Configure `claude_desktop_config.json` for MCP server integration

## Tools and Integration

### Essential Tools
- GitHub CLI (`gh`) for repository management
- Bash environment for system operations
- MCP servers for extended functionality
- Git worktrees for parallel development

### Subagents and Task Delegation
- Use subagents for complex, multi-step problems
- Delegate specific tasks to focused Claude instances
- Implement task coordination between multiple agents

## Key Recommendations

### Communication and Direction
- Be specific and detailed in instructions
- Course-correct early when Claude deviates from intended path
- Use `/clear` command to maintain context and focus
- Provide immediate feedback on Claude's approach

### Iteration and Improvement
- Expect 2-3 iterations for optimal results
- Allow Claude to see and evaluate its own outputs
- Use visual feedback loops for UI/UX development
- Experiment with different approaches and adapt workflows

### Context Management
- Store prompt templates in `.claude/commands` folder
- Use `--mcp-debug` flag for configuration troubleshooting
- Maintain clean context with regular `/clear` usage
- Document successful patterns in `CLAUDE.md`

## Development Environment Setup

### Claude Desktop Configuration
```json
{
  "mcpServers": {
    "puppeteer": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-puppeteer"]
    }
  }
}
```

### Recommended Project Structure
```
project/
├── CLAUDE.md              # Project-specific instructions
├── .claude/
│   ├── settings.json      # Persistent configurations
│   └── commands/          # Prompt templates
├── src/                   # Source code
└── tests/                 # Test files
```

## Workflow Optimization

### For Repeated Tasks
- Create templates for common development patterns
- Use headless mode for automated workflows
- Implement feedback loops with visual validation
- Store successful approaches in documentation

### For Complex Features
- Break down into smaller, manageable tasks
- Use the TodoWrite tool for task tracking
- Implement incremental development with regular commits
- Validate each step before proceeding

## Best Practices Summary
1. **Setup**: Proper `CLAUDE.md` and tool permissions
2. **Workflow**: Explore-Plan-Code-Commit approach
3. **Testing**: Test-driven development methodology
4. **Visual**: Screenshot-driven iteration for UI
5. **Automation**: Headless mode for CI/CD integration
6. **Communication**: Specific instructions and early correction
7. **Context**: Clean context management with `/clear`
8. **Iteration**: Allow 2-3 cycles for optimal results