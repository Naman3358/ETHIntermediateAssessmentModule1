# Value Manager

## DESCRIPTION

Value Manager is a simple Solidity smart contract for managing a single integer value with specific constraints. It includes basic functions for setting, retrieving, and validating the value, ensuring only the contract owner can modify it.

## ## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Functions {
    address public owner;
    uint256 public value;

    constructor() {
        owner = msg.sender;
    }

    function setValue(uint256 _newValue) external onlyOwner {
        require(_newValue != 0, "The new value cannot be zero");
        value = _newValue;
    }

    function assertFunction(uint256 _num) external pure returns (uint256) {
        assert(_num != 0);
        return _num;
    }

    function revertFunction(uint256 _num) external pure returns (uint256) {
        require(_num != 0, "The number cannot be zero");
        return _num;
    }

    function retrieve() external view returns (uint256) {
        return value;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can call this function");
        _;
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

## Help
For any assistance or queries, feel free to reach out to the contract author via [email](namansharma272004@gmail.com).


## Authors
Naman Sharma


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
