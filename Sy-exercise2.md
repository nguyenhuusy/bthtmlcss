console.log('haha')
// Ex for Interface Segregation Principle
//ISP: Validate only if it is necessary
class UserISP {
    constructor(username, password, validate) {
      this.username = username;
      this.password = password;
      this.validate = validate;
  
      if (validate) {
        this.initiateUser(username, password);
      } else {
        console.log("no validation required");
      }
    }
  
    initiateUser() {
      this.validateUser(this.username, this.password);
    }
  
    validateUser = (username, password) => {
      console.log("validating...");
    }
  }
  
  //User with validation required
  console.log(new UserISP("Francesco", "123456", true));
  // validating...
  // UserISP {
  //   validateUser: [Function: validateUser],
  //   username: 'Francesco',
  //   password: '123456',
  //   validate: true
  // }
  
  
  //User with no validation required
  console.log(new UserISP("guest", "guest", false));
  // no validation required
  // UserISP {
  //   validateUser: [Function: validateUser],
  //   username: 'guest',
  //   password: 'guest',
  //   validate: false
  // }

//Ex for Dependency Inversion Principle
import React, { Component } from 'react';
class NavItem extends Component {
  render() {
    const { label, link } = this.props;

    return (
      <li className="nav-item">
        <Link className="nav-link" to={ link }>{ label }</Link>
      </li>
    )
  }
}