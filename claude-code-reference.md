# Claude Code - Shortcuts & Techniques Reference

## Essential Slash Commands

### Help & Documentation
- `/help` - Get help with using Claude Code
- `/docs` - Access documentation

### File Operations
- `/open <file>` - Open a specific file
- `/search <query>` - Search across the codebase
- `/find <pattern>` - Find files matching a pattern

### Git Operations
- `/commit` - Create a git commit with AI-generated message
- `/push` - Push changes to remote repository
- `/status` - Show git status
- `/diff` - Show git differences

### Development Tools
- `/test` - Run tests in the project
- `/build` - Build the project
- `/lint` - Run linting tools
- `/format` - Format code

## Tool Usage Best Practices

### File Management
- **Read before Edit**: Always use `Read` tool before making edits
- **Use MultiEdit**: For multiple changes in the same file
- **Absolute Paths**: Always use absolute paths, never relative ones

### Search Strategies
- **Glob**: Find files by pattern (`**/*.js`, `src/**/*.ts`)
- **Grep**: Search file contents with regex patterns
- **Task Agent**: Use for complex, multi-round searches

### Code Navigation
- **Line References**: Use `file_path:line_number` format for precise references
- **Context Reading**: Read surrounding code to understand patterns and conventions

## Efficient Workflows

### Planning Complex Tasks
1. Use `TodoWrite` tool to break down complex tasks
2. Mark tasks as `in_progress` before starting
3. Complete tasks one at a time
4. Mark as `completed` immediately after finishing

### Code Changes
1. **Understand First**: Read existing code and conventions
2. **Follow Patterns**: Mimic existing code style and structure
3. **Test Changes**: Run tests and linting after modifications
4. **Verify**: Use diagnostics to check for errors

### Parallel Operations
- Batch multiple independent tool calls in a single message
- Use multiple `Bash` commands simultaneously for git operations
- Run searches in parallel when exploring codebase

## Advanced Techniques

### Background Tasks
- Use `run_in_background` for long-running commands
- Monitor with `BashOutput` tool
- Kill with `KillShell` when needed

### Web Integration
- `WebFetch` for external documentation and resources
- `WebSearch` for current information beyond knowledge cutoff

### Project Analysis
- Check `package.json`/`cargo.toml` for available libraries
- Examine existing components before creating new ones
- Use `mcp__ide__getDiagnostics` for VS Code integration

## Code Quality Standards

### Security Best Practices
- Never expose or log secrets/keys
- Follow defensive security principles only
- Avoid malicious code assistance

### Code Style Guidelines
- No comments unless explicitly requested
- Follow existing conventions in the codebase
- Use idiomatic patterns for the language/framework

### Testing & Validation
- Always run lint/typecheck commands after changes
- Never assume test frameworks - check documentation
- Verify solutions with appropriate tests

## Common Patterns

### File Reading Strategy
```
1. Use Glob to find relevant files
2. Read key files to understand structure
3. Use Grep to find specific implementations
4. Read target files before making changes
```

### Error Handling Workflow
```
1. Run build/test commands
2. Analyze error output
3. Create todos for each error
4. Fix systematically
5. Verify fixes with re-run
```

### Codebase Exploration
```
1. Check README/docs for project structure
2. Examine package.json for dependencies
3. Look at existing similar components
4. Follow import patterns and conventions
```

## Keyboard & CLI Tips

### Efficient Communication
- Keep responses concise (under 4 lines typically)
- Use direct answers without preamble
- Provide one-word answers when appropriate

### File Naming Conventions
- Use descriptive, specific names
- Follow project's existing naming patterns
- Avoid generic names like "utils" or "helpers"

### Git Commit Best Practices
- Focus on "why" rather than "what"
- Use conventional commit formats if project uses them
- Include Claude Code attribution when creating commits

## Troubleshooting

### Common Issues
- **Hook Blocks**: Adjust actions based on hook feedback
- **Path Issues**: Always use absolute paths with proper quoting
- **Search Failures**: Use Task agent for complex searches
- **Build Failures**: Check diagnostics and fix systematically

### Performance Optimization
- Batch tool calls when possible
- Use specialized agents for their intended purposes
- Limit file reads to necessary content only
- Use head_limit for large search results

## Quick Reference Commands

### Essential Bash Commands
- `ls` - List directory contents
- `pwd` - Show current directory
- `git status` - Check repository status
- `npm run <script>` - Run package scripts
- `rg <pattern>` - Search with ripgrep

### File Operations
- Read file: Use `Read` tool
- Edit file: Use `Edit` or `MultiEdit` tool
- Create file: Use `Write` tool (only when necessary)
- Search files: Use `Grep` or `Glob` tool

## Remember
- Always plan complex tasks with TodoWrite
- Read before you write
- Follow existing patterns
- Test your changes
- Keep responses concise
- Use absolute paths
- Batch operations when possible
