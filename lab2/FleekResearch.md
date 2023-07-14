## Steps:

The following steps were taken to set up the project on Fleek:

1. Added a new site on Fleek.
2. Connected the site to a GitHub repository.
3. Selected the desired repository and branch to deploy.
4. Chose the Docker image "node:lts" for the build environment.
5. Left other settings at their default values.

### Configuration Settings:

- Custom Domains: I configured a custom domain for the deployed project, which is `https://snowy-bar-1972.on.fleek.co/`.
- SSL/TLS Encryption: Fleek automatically provides SSL/TLS encryption for the custom domain, ensuring secure
  communication with the deployed project.
- CDN Integration: Fleek utilizes a Content Delivery Network (CDN) to optimize content delivery and enhance performance.
  The specifics of the CDN integration can be found in the Fleek documentation.

### IPFS Link and Custom Domain:

- IPFS Link: The IPFS link for the deployed project
  is `https://fleek.ipfs.io/ipfs/QmZyMTSEfLpsUR6W14R26UP3GzCFj4kaRV7mi7Ax7S3oeV/`.
- Custom Domain: The custom domain associated with the project is `https://snowy-bar-1972.on.fleek.co/`.

### Observations:

During the setup process, I discovered the ease of deploying website files using Docker images. This approach proved to
be highly convenient in this particular case. Fleek's platform offers continuous deployment capabilities, enabling
seamless updates and changes to the deployed project.
