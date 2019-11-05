[<< Back to Methodology](index.md)

# Continuous Integration
Continuous integration is the practice of merging all developer working copies to a shared mainline on a highly frequent basis.  CI mitigates merge / integration hell by merging early and often.  It greatly depends on robust, automated unit tests that are run on every build, which is triggered upon every commit (or, after a slight delaying trigger).  

# Best Practices
- Maintain a code repository
- Automate the build
- Make the build self-testing
- Everyone commits to the baseline every day
- Every commit should be built
- Keep the build fast
- Test in a clone of the production environment
- Make it easy to get the latest deliverables
- Everyone can see the results of the latest build
- Automate deployment
