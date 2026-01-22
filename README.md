# custom-assembly-as-code
Declarative trigger custom image builds using IaC:
* Verify integrity of existing image by validating the digital signature with cosign
* Verify SBOM attestation and list packages
* Trigger new build using the APKO Overlay YAML in the ca-images-iac folder
* Adheres to security least privilege by using short-lived ephemeral tokens to:
  * Authenticate to the Chainguard Registry using an [assumed identity](https://edu.chainguard.dev/chainguard/administration/iam-organizations/assumable-ids/) (using the ambient creds of each workflow invocation)
  * Authenticate to GitHub (using [octo-sts](https://www.chainguard.dev/unchained/the-end-of-github-pats-you-cant-leak-what-you-dont-have) in place of a long-lived PAT) 
 
## Usage

* Edit the ca-images-iac yaml declarations to add packages [adding-custom-annotations-and-environment-variables ](https://edu.chainguard.dev/chainguard/chainguard-images/features/ca-docs/custom-assembly-chainctl/#adding-custom-annotations-and-environment-variables)
* Commit to the main branch
* Merge
* Profit 
