# REC Processes

## Principles (Testning)
* Major version = breaking changes allowed (3.0, 4.0..)
* Minor version = new features added (modules), (2.4, 2.5, …)
* Third-level version = Bugfix release, spell changes, etc (2.3.1, 2.3.2..)
* Do release planning and milestones on GitHub (e.g., the latter bits of this document, once we’re done with it)

## Roles
* Release engineering team: Karl Hammar, Erik Wallin, Joakim Eriksson
* How to extend with other interested parties?

# Testing Process
* Presently just manual sanity checking. Not sustainable long-term. Needs to be developed and integrated w/ release process below.

# Release Process
1. Merge any completed feature branches.
2. Update Version IRI in all ontologies, and in all owl:imports clauses
3. Push to GitHub
4. Make a release on GitHub, adding a tag named “vX.Y” in alignment with the release number (note the leading v)
5. (If needed) update WIDOCO-configuration files in https://github.com/RealEstateCore/doc
6. Update documentation in https://github.com/RealEstateCore/doc (presently generated manually w/ WIDOCO, workflow may need to be automated).
7. Update w3id.org redirects; fork https://github.com/perma-id/w3id.org, update own fork, pull request to integrate
8. Write a press release (?)
