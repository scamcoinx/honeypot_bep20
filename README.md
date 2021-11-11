# honeypot_bep20
// The second part of HoneyPot BEP20 Smart Contract you can buy in Telegram for 1 BNB: https://t.me/scamcoinx //


pragma solidity >=0.5.17;

library SafeMath {

  function add(uint a, uint b) internal pure returns (uint c) {

    c = a + b;

    require(c >= a);

  }

  function sub(uint a, uint b) internal pure returns (uint c) {

    require(b <= a);

    c = a - b;

  }

  function mul(uint a, uint b) internal pure returns (uint c) {

    c = a * b;

    require(a == 0 || c / a == b);

  }

  function div(uint a, uint b) internal pure returns (uint c) {

    require(b > 0);

    c = a / b;

  }

}

contract BEP20Interface {

  function totalSupply() public view returns (uint);

  function balanceOf(address tokenOwner) public view returns (uint balance);

  function allowance(address tokenOwner, address spender) public view returns (uint remaining);

  function transfer(address to, uint tokens) public returns (bool success);

  function approve(address spender, uint tokens) public returns (bool success);

  function transferFrom(address from, address to, uint tokens) public returns (bool success);

  event Transfer(address indexed from, address indexed to, uint tokens);

  event Approval(address indexed tokenOwner, address indexed spender, uint tokens);

}

contract ApproveAndCallFallBack {

  function receiveApproval(address from, uint256 tokens, address token, bytes memory data) public;

}


// The second part of HoneyPot BEP20 Smart Contract you can buy in Telegram for 1 BNB: https://t.me/scamcoinx //
