# README
Welcome to the CV Updater! 
Managing your CV can be complex, but this tool breaks it down into easy steps. No coding background needed! Follow along to keep your CV current. Plus, explore GitHub, Docker, and GitHub Actions for a deeper dive into tech skills, even for non-developers.

# Devcontainer
```json
// For format details, see https://aka.ms/devcontainer.json. 
{
	"name": "Debian",
	// Use a Dockerfile or Docker Compose file. More info: https://containers.dev/guide/dockerfile
	"build": {
		"dockerfile": "Dockerfile"
	},

	// Features to add to the dev container. More info: https://containers.dev/features.
	"features": {
		"ghcr.io/prulloac/devcontainer-features/latex:1": {}
	},

	// Use 'postCreateCommand' to run commands after the container is created.
	"postCreateCommand": "tlmgr option sys_bin /usr/local/bin && tlmgr path add"
}
```

# Dockerfile
```Dockerfile
# Use docker image
FROM debian:bookworm-slim

# Set locales
RUN apt-get update 
RUN apt-get install -y locales
RUN rm -rf /var/lib/apt/lists/* 
RUN localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8
```