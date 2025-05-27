# Actions & Power Automate Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio action YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow and action integration guidelines.

Check and improve:
1. Connection reference configuration and security
2. Input/output variable mapping and validation
3. Error handling and recovery mechanisms
4. User communication during action execution
5. Authentication and authorization settings
6. Performance considerations and timeouts
7. Integration with conversation flow
8. YAML structure and action metadata

Focus on official Microsoft recommendations for Power Automate integration, security best practices, and user experience during action execution. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Actions & Power Automate Checklist
- [ ] Connection reference properly configured
- [ ] Authentication mode and security settings appropriate
- [ ] Input variable mapping clear and validated
- [ ] Output variable handling optimized
- [ ] Error handling robust and user-friendly
- [ ] User communication during execution
- [ ] Performance timeouts configured
- [ ] Integration with conversation flow seamless

### 🎯 Key Configuration Areas

**Connection Configuration:**
- Connection reference setup and naming
- Authentication mode selection (Invoker vs Service)
- Security and access control considerations
- Connection sharing and reusability

**Variable Mapping:**
- Input parameter validation and formatting
- Output variable assignment and processing
- Data type handling and conversion
- Variable scope management

**Error Handling:**
- Connection failure scenarios
- Action execution errors
- Timeout handling
- User-friendly error messaging
- Recovery and retry mechanisms

**User Experience:**
- Loading messages during execution
- Progress indicators for long-running actions
- Clear success and failure communication
- Seamless integration with conversation flow

### 🔒 Security Considerations
- Authentication method selection
- Data privacy and protection
- Access control and permissions
- Secure parameter passing
- Audit and compliance requirements

### ⚡ Performance Optimization
- Action timeout configuration
- Asynchronous execution patterns
- Resource usage optimization
- Caching strategies for repeated calls
- Load balancing considerations

### 📚 Reference Guidelines
- [Power Automate Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow)
- [Connection Management](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow#use-flows-in-your-copilot)
- [Security Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-overview)
