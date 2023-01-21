# my-cv-project

This is a small project that uses `Strapi` as the **Back-end** and a **Front-end** framework like React to create a basic CV website.

## Back-end

- Create a new Strapi project by running npx create-strapi-app my-cv-project in the command line.
- Once the project is set up, navigate to the project folder and start the server by running npm run develop.
- In the Strapi Admin panel, create a new content type called "Experience" with fields for the company name, job title, dates, and a description.
- Create another content type called "Education" with fields for the school name, degree, field of study, and dates.
- Create a third content type called "Skills" with fields for the skill name and a level (beginner, intermediate, advanced).
- Create a fourth content type called "About" that will have a single text field for the user to describe about themselves.
- Once the content types are set up, use the Strapi API to create and manage the data for each of the sections of the CV (Experience, Education, Skills, and About).
  
<details>
 
<summary> 
To create new data, you can use the POST method, for example</summary>

```js
axios.post('http://localhost:1337/experiences', {
    company_name: 'ACME Inc.',
    job_title: 'Software Engineer',
    start_date: '2022-01-01',
    end_date: '2022-12-31',
    description: 'Worked on various projects using React, Node.js and MongoDB'
  })
  .then(response => {
    console.log(response);
  })
  .catch(error => {
    console.log(error);
  });
  ```

  </details>

  <details>

  <summary>
  To retrieve data, you can use the GET method, for example</summary>

```js
axios.get('http://localhost:1337/experiences')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.log(error);
  });
```
  </details>

  <details>

  <summary>to delete data, you can use the DELETE method, for example</summary>

```js
axios.delete('http://localhost:1337/experiences/1')
  .then(response => {
    console.log(response);
  })
  .catch(error => {
console.log(error);
});
```
</details>

<details>
<summary> Note</summary>

You can use these API calls in your frontend code, in order to create, retrieve, update, and delete data for the different sections of your CV.

It's worth noting that the URLs and data in the examples above are just for demonstration purposes, and you'll need to adjust them to match your specific setup. Additionally, you'll want to make sure to handle any errors that may occur during the API calls and display appropriate messages to the user.

</details>

<details>

<summary>Where you should store CV data content?</summary>

store the data for your CV content in a database. Strapi supports several databases like MongoDB, MySQL, and PostgreSQL. You can choose the one you are most comfortable with. Once you have set up the database, Strapi will automatically create the database tables and models based on the content types you have created.

Then you can use the Strapi API to create, retrieve, update and delete data for each of the sections of your CV (Experience, Education, Skills, and About). The API calls for creating, retrieving, updating and deleting data that I provided in my previous answer, are making requests to the database via the Strapi API.

You can also use a front-end library like axios to make HTTP requests to the Strapi API and interact with the data stored in the database.

It's important to mention that you can also use a different approach to store your data, like using a cloud-based database service like Firebase, AWS DynamoDB, or Google Cloud Firestore

</details>
  
## Front-end

- Create a new React project by running npx create-react-app my-cv-project-front-end.
- In the front-end project, install the necessary dependencies such as **axios** for making API calls to **Strapi**
- Use the Strapi API to fetch data for each of the sections of the CV (Experience, Education, Skills, and About) and display them on the website.
- Create a basic layout for the CV website, with sections for each of the content types and a way to navigate between them.
- Use styling libraries like Bootstrap or Material-UI to make the website look presentable
