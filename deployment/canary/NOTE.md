## Blue–Green Deployment

Blue–Green Deployment is a release strategy that uses **two identical environments** to reduce downtime and risk during deployments.

### How It Works
- **Blue**: current production environment
- **Green**: new version of the application
- Deploy the new version to **Green** while **Blue** keeps serving users
- Test the Green environment
- Switch traffic from Blue to Green
- Roll back instantly by switching back to Blue if problems occur

### Benefits
✅ Zero downtime
✅ Fast and safe rollback
✅ Lower deployment risk

### Key Idea
Only one environment is live at a time, and switching between them is quick and reversible.
