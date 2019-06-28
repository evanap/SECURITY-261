## Scrub GitHub credentials from build.xml files

GitHub Pull Request Builder Plugin before 1.40.0 stored GitHub credentials in `build.xml` files as part of serialized Java objects. 1.40.0 stopped doing so, but does not remove previously serialized data.

See the [2018-03-26 Jenkins security advisory](https://jenkins.io/security/advisory/2018-03-26/#SECURITY-261).

The script in this repository will attempt to save old build records again, scrubbing the credentials from disk.

**We strongly recommend that old access tokens be revoked even if running this script.**

### How to use

1. Create a freestyle job.
1. Check on *Restrict where this project can be run*, write the label *master* so it only run on the master node.
1. Add a *Execute system Groovy script* build step.
1. Paste the entire content of the `script.groovy` in this repository into the text box.
1. Save and click *Build Now* to run the job.
1. Read the output and act on instructions as necessary.
