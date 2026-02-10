---
icon: lucide/rocket
tags:
  - deployment
  - verification
  - playwright
  - ultrathink
---

# Deployment Verifier

Deploy, verify, and screenshot-test the live site.

## Prompt

```title="Copy and paste into agent session"
Deploy to vercel and verify that the deployment worked properly without any
errors (iterate and fix if there were errors). Then visit the live site with
playwright as both desktop and mobile browser and take screenshots and check for
js errors and look at the screenshots for potential problems and iterate and fix
them all super carefully!
```

## When to Use

- After deploying to production
- For automated deployment verification
- To catch runtime issues that static analysis misses

## Tips

- Test both desktop and mobile viewports
- Check browser console for JS errors
- Screenshots help catch visual regressions
- Replace "vercel" with your deployment target if different
