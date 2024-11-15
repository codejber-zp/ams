# AMS
AMS is monorepo created with Nx. It contains multiple applications and libraries. 
The purpose is to create all in one solution for associations and other people based organizations.

Functionalities are breaked down into multiple applications.

## LMS
LMS is Learning Management System. It is used to manage courses, students, teachers and other related entities.

NextJS based. Dockerized.

## Run tasks

To run the dev server for your app, use:

```sh
pnpx nx dev lms
```

To create a production bundle:

```sh
pnpx nx build lms
```
or to create a production bundle and serve it inside docker container on localhost:3000:
```shell
pnpx nx run lms:container && docker run -p 3000:3000 lms:main
```


To see all available targets to run for a project, run:

```sh
pnpx nx show project lms
```

These targets are either [inferred automatically](https://nx.dev/concepts/inferred-tasks?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) or defined in the `project.json` or `package.json` files.

[More about running tasks in the docs &raquo;](https://nx.dev/features/run-tasks?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

## Add new projects

While you could add new projects to your workspace manually, you might want to leverage [Nx plugins](https://nx.dev/concepts/nx-plugins?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) and their [code generation](https://nx.dev/features/generate-code?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) feature.

Use the plugin's generator to create new projects.

To generate a new application, use:

```sh
pnpx nx g @nx/next:app demo
```

To generate a new library, use:

```sh
pnpx nx g @nx/react:lib mylib
```

You can use `pnpx nx list` to get a list of installed plugins. Then, run `pnpx nx list <plugin-name>` to learn about more specific capabilities of a particular plugin. Alternatively, [install Nx Console](https://nx.dev/getting-started/editor-setup?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) to browse plugins and generators in your IDE.

[Learn more about Nx plugins &raquo;](https://nx.dev/concepts/nx-plugins?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects) | [Browse the plugin registry &raquo;](https://nx.dev/plugin-registry?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)


[Learn more about Nx on CI](https://nx.dev/ci/intro/ci-with-nx#ready-get-started-with-your-provider?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)

## Install Nx Console

Nx Console is an editor extension that enriches your developer experience. It lets you run tasks, generate code, and improves code autocompletion in your IDE. It is available for VSCode and IntelliJ.

[Install Nx Console &raquo;](https://nx.dev/getting-started/editor-setup?utm_source=nx_project&utm_medium=readme&utm_campaign=nx_projects)
