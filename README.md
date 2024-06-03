# Network Gaming DevOps Tech Test

This tech test is designed to give an overview of our full tech stack. You will need to demonstrate an 
understanding of each part of the stack, and the motivations behind why they were used.

Within this mono-repo, you should build:

- A backend web server, written in [Go](https://go.dev/), which exports a single endpoint that returns a random integer 
between an upper and lower limit, dictated by query params
  - Assume that if no lower limit is defined then lower limit is 1
  - Assume that if no upper limit is defined then upper limit is 100
  - Enforce validation such that if lower limit is defined, it must be greater than or equal to 1
  - Enforce validation such that if upper limit is defined, it must be less than or equal to 100
  - Enforce validation such that lower limit cannot be greater than upper limit
  - This application should be containerised


- A single page web app, written in [Angular](https://angular.io/) which calls the endpoint from the above backend server
to render a random integer between 1 and 20
  - A random number should be rendered on page load
  - A button should be included to 're-roll' the number
  - This doesn't need to be styled too much, so focus more on logic and less on aesthetics


- Infrastructure as code, to support the deployment of these applications to [AWS](https://aws.amazon.com/)
  - This should include [Terraform](https://www.terraform.io/) to provision
    - A VPC
    - Servers to host the backend application, with load balancers and security groups
    - A CDN to host the frontend application
  - And [Ansible](https://www.ansible.com/) to install [`ec2-instance-connect-cli`](https://github.com/aws/aws-ec2-instance-connect-cli)
  on the servers hosting the backend application, so that you can ssh onto the servers without use of the server's PEM key


- Shell scripts to automate the deployment of both the frontend and backend applications to the cloud, 
and to automate the connection to the servers hosting the backend application

You will be marked on the code you write, and you will need to demonstrate an understanding of each element of tech 
in a technical interview