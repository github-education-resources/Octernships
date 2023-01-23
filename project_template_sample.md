>> This is a sample project template for inspiration 
# Octernship Information
<img src="https://user-images.githubusercontent.com/53075480/213182217-c8ef7bd5-9ffe-4201-9763-c157206a5910.png" width="100">

### Company information 
<!--- Use this section to share information about your company such as founding information, mission statement, product description, product success, etc.--->
GitHub is the developer company. We make it easier for developers to be developers: to work together, to solve challenging problems, and to create the world’s most important technologies. We foster a collaborative community that can come together—as individuals and in teams—to create the future of software and make a difference in the world.

### Why participate in an Octernship with GitHub
<!--- Use this section to appeal to students. Consider sharing information about recent projects, the technology stack, the type of mentorship students can expect, listing future employment opportunities, etc. --->
GitHub is changing the way the world builds software, and we want you to help build GitHub!
Our team actively contributes back to the wider open source community, including the Node.js Project, OpenJS Foundation, Open Source Security Foundation & TC39.
In this role, you will have the opportunity to work as a full-stack engineer with a distributed, diverse & passionate team delivering features & improvements to our open source projects. You’ll get to work closely with external community contributors as well as internal stakeholders from engineering, design, security, support, product & leadership. Your work will have a direct impact on the lives of millions of developers around the world.

### Octernship role description
<!--- Use this section to describe the role in as much detail as necessary. Please include the GitHub Classroom assignment submission date, length of the Octernship, and the monthly stipend --->
We're looking for a full-stack developer to join the npm CLI team. This team is responsible for the open source tools that empower the JavaScript ecosystem to create, distribute & consume packages.

| Octernship info  | Timelines and Stipend |
| ------------- | ------------- |
| Assignment Deadline  | 26 March 2023  |
| Octernship Duration  | 3 Months  |
| Monthly Stipend  | $700 USD  |

### Recommended qualifications
<!--- Use this section to describe what skills a student might need to complete the problem statement on GitHub Classroom --->
- Experience with Git & GitHub
- Writing modern JavaScript/Node.js
- Passion for open source & web standards

### Eligibility
To participate, you must be:
* A [verified student](https://education.github.com/discount_requests/pack_application) on Global Campus
* 18 years or older
* Active contributor on GitHub (monthly)

# Assignment
## Recursive rm in npm CLI

### Task instructions
<!--- Use this section to describe the task that students are required to complete. We ask that you also include instructions on running and preparing the students' local environment if necessary. --->
Use recursive rm in cli command and add test case. Currently npm ci fails with ERR_FS_EISDIR for node_modules/.bin

#### Steps To Reproduce
- Fork this repository
- Install npm

Use this package.json for testing

```
{
  "name": "npm-test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "eslint": "^8.31.0"
  }
}
```



### Task Expectations
<!--- Please add expectations that students need to follow to be considered. Some examples include: completing the task on their own, not using code from external resources without comprehending the logic, etc.  --->
- The cli should delete node_modules without crashing
- The task should be completed on your own
- Using code from external sources must reference it's logic and source 


### Task submission

Students are expected to use the [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow) when working on their task. This includes

1. Creating a new branch
2. Making changes on the new branch to complete the task
3. Opening a Pull Request for review

### Resources
<!--- Use this section to add resources for students to refer to. For example: Documentation, Tutorials, Guides, and more.  --->
- Install [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- npm [documentation](https://docs.npmjs.com/)
- Sample [Issue](https://github.com/npm/cli/issues/6051)
