# [Backstage](https://backstage.io)

# Workshop
This workshop is designed to be run leveraging VSCode DevContainers. After cloning this repository re-open it in a dev container.

## Start Backstage

### Stand Up Database
Run the following command in a terminal:
```sh
docker compose up
```

### Start Backstage
Open another terminal if needed and run the following commands:
```sh
yarn install
yarn dev
```

### Explore Backstage
Backstage will open on http://localhost:3000. You can explore the different components of backstage.

#### Home
In this view you can view the different `entity types` available by default in Backstage. You can add your own if you'd like. By default Backstage comes with:
- Component
- Group
- Location
- System
- Template
- User

This repo comes with the group `cool-kids` and the default `Node.js` template. We will add other entities throughout the workshop.

#### APIs
There won't be anything here yet.

#### Docs
There won't be anything here yet but we will add Docs later.

#### Create
Here you will see the example Node.JS template. We will use this later in the workshop.

## Add Entities

We will be leveraging the following [gcp-microservices-demo](https://github.com/dillon-courts/gcp-microservices-demo) to explore the software catalog concept and add entities.

### Add a System
Navigate to the `Create` section and client on `Register Existing Component`.

![register-component](./screenshots/register-component.png)

Enter the url of the catalog-info.yml file
```
https://github.com/dillon-courts/gcp-microservices-demo/blob/main/catalog-info.yaml
```

![register-component-url](./screenshots/register-component-url.png)

Click `Analyze` and then click through the next steps to import and add the component. You should now be able to view the entity under the `System` Kind on the Home page.

![system-component](./screenshots/system-component.png)

### Add several components of the system

Use the same process as above to add additional components of the system.

Add at least the following components so you can see how they fit together. You can add additional components if you'd like, each service within the [src directory](https://github.com/dillon-courts/gcp-microservices-demo/tree/main/src) contains a `catalog-info.yaml` file.

- https://github.com/dillon-courts/gcp-microservices-demo/blob/main/src/adservice/catalog-info.yaml
- https://github.com/dillon-courts/gcp-microservices-demo/tree/main/src/cartservice
- https://github.com/dillon-courts/gcp-microservices-demo/blob/main/src/checkoutservice/catalog-info.yaml

1. Go to the create section
2. Click `Register Existing Component`
3. Enter the URL of a catalog-info.yml file
4. Click `Analyze` and then `Import`

Once complete you should see all components registered on the Home page as Kind `Component`.

![catalog-components](./screenshots/catalog-components.png)

If you go view your `ms-demo` system you will see the connections have been generated in a graph like structure.

![system-graph](./screenshots/system-graph.png)

## Tech Docs