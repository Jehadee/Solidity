# My Token

This Solidity program serves as a basic demonstration of the syntax and features of the Solidity programming language, under the name "My Token". It is designed to provide beginners with a foundational understanding of Solidity and its operations.

## Description

This software is a basic agreement coded in Solidity, a programming language utilized for creating smart contracts on the Ethereum blockchain. The agreement consists of a solitary function that provides the output "My Token". This software acts as a straightforward and uncomplicated initiation to Solidity programming, and can serve as a foundation for more intricate projects in the times ahead.

## Getting Started

### Installing

To download the code, follow these steps:

Visit the Solidity repository on Github.
Click on the green "Code" button and then click "Download ZIP".
Extract the downloaded ZIP file to a local directory.
After downloading the code, you will find the MyToken contract in the contracts folder. No modifications are needed to be made to the files or folders.

To run the program, you will need to set up a local development environment for Solidity. Here's a step-by-step guide:

1. Install Node.js from the official website.
2. Install Truffle using npm by running the following command:
bash
npm install -g truffle

3.Navigate to the MyToken contract directory in your terminal/command prompt.
4. Compile the contract by running the following command:
bash
truffle compile

5. Create a new Truffle project in the same directory by running the following command:
bash
truffle init

6. Move the compiled contract artifacts to the build/contracts folder of the Truffle project by running the following command:
bash
mv build/contracts/MyToken.json migrations/2_deploy_contracts.js

7. Edit the migrations/2_deploy_contracts.js file to deploy the MyToken contract:
javascript
const MyToken = artifacts.require("MyToken");

module.exports = function (deployer) {
  deployer.deploy(MyToken);
};

8. Deploy the contract to a local blockchain by running the following command:
bash
truffle develop
truffle(develop)> migrate
Now you have successfully downloaded, compiled, and deployed the MyToken contract!

If you encounter any issues, you can refer to the Truffle documentation for help:

Truffle documentation
The authors of the MyToken contract are:

Jehadee
The MyToken contract is licensed under the MIT License. You can find the license in the LICENSE file.

### Executing program

In order to execute this program, you have the option to utilize Remix, an online Solidity IDE. To commence, navigate to the Remix website located at https://remix.ethereum.org/.

Upon reaching the Remix website, initiate the creation of a new file by selecting the "+" icon situated in the left-hand sidebar. Save the file with a .sol extension (for example, MyToken.sol). Proceed by copying and pasting the provided code into the file.

pragma solidity 0.8.18;

contract MyToken {
    
    // public variables here
    string public name = "My Token";
    string public symbol = "MTK";
    uint256 public totalSupply;
    
    // mapping variable here
    mapping(address => uint256) public balanceOf;
    // mint function
    function mint(address account, uint256 amount) public {
        totalSupply += amount;
        balanceOf[account] += amount;
        emit Transfer(address(0), account, amount);
    }
    // burn function
    function burn(address account, uint256 amount) public {
        require(balanceOf[account] >= amount, "Insufficient balance");
        totalSupply -= amount;
        balanceOf[account] -= amount;
        emit Transfer(account, address(0), amount);
    }
      event Transfer(
        address indexed from,
        address indexed to,
        uint256 value
    );

    constructor() {
        totalSupply = 1000000 * (10 ** uint256(decimals()));
        balanceOf[msg.sender] = totalSupply;
        emit Transfer(address(0), msg.sender, totalSupply);
    }
    function decimals() public pure returns (uint8) {
        return 18;
    }
}
}

- To compile the code, access the "Solidity Compiler" tab located in the sidebar on the left-hand side. Ensure that the "Compiler" option is set to "0.8.4" or any other compatible version. Afterward, proceed to click on the "Compile MyToken.sol" button.

- Once the code has been successfully compiled, you can deploy the contract by navigating to the "Deploy & Run Transactions" tab in the left-hand sidebar. From the dropdown menu, select the "MyToken" contract and then click on the "Deploy" button.

- Once the contract has been deployed, you can interact with it by invoking the mint function. Locate the "HelloWorld" contract in the left-hand sidebar and click on the "mint" function. Finally, execute the function and The contract owner can utilize this feature to create additional tokens and allocate them to a designated address. Subsequently, the totalSupply and balanceOf variables will be adjusted accordingly. Moreover, the Transfer event will be triggered to inform external entities about the transaction.

- The contract owner has the ability to destroy a specific quantity of tokens from a designated address using this function. Prior to proceeding, the require statement verifies if the sender possesses enough balance. The totalSupply and balanceOf variables are then adjusted accordingly, and the Transfer event is emitted.

- The Transfer event is declared in this line, and it is emitted whenever tokens are transferred between addresses.

- This is the constructor function that gets executed upon deployment of the contract. It sets the values for totalSupply and balanceOf variables and triggers a Transfer event to inform that the initial supply has been transferred to the address of the contract creator.

- This particular function provides the count of decimal places utilized by the token. In this instance, it is configured to 18, which is the customary value for ERC20 tokens.



## Help

Here are some common issues and challenges that may arise when working with Solidity and Remix:

1. Ensure you are using the correct version of Solidity for your contract by specifying it in the pragma statement at the top of your contract file.
2. Check for syntax errors in your Solidity code and ensure it is properly formatted. Consider using a Solidity linter to help identify syntax errors.
3. Verify that your contract compiles without any errors. If compilation errors occur, review the error messages for insights into the issue.
4. Confirm that your contract deploys successfully. If deployment errors occur, examine the error messages for details on the problem.
5. Set a reasonable gas limit for your contract to avoid gas estimation errors. If such errors arise, try increasing the gas limit.
6. Ensure that your contract tests are accurately written and pass successfully. If testing errors occur, review the error messages for guidance.

If you encounter any challenges while working with Solidity and Remix, consider consulting the following resources for assistance:

- Solidity documentation
- Remix documentation
- Solidity community forum
- Solidity Stack Overflow

To provide additional information in your program, consider the following methods:

- Include comments in your Solidity code for explanatory notes.
- Write documentation for your contract using the NatSpec format.
- Add helper information to your Remix project using the "Comments" tab in the right-hand panel.

To execute a command in Remix, navigate to the "Run" tab in the right-hand panel. Select the desired environment (e.g., JavaScript VM, Injected Web3) and enter the command in the "Run" field.

For instance, if your contract features a totalSupply function, you can run the command in Remix to retrieve the total supply of tokens.

## Authors

Contributors names and contact info

Jehadee L. Macadato
ex. [@chubby](https://www.facebook.com/profile.php?id=100016832777306)


## License

This project is licensed under the Jehadee License - see the LICENSE.md file for details
