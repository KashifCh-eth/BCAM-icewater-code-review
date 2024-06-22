
 
## Contract Mistakes or logical errors  

1.  --> contracts/H2OIceVirtualPool.sol:20:10:
   |
20 |     I am a bug
   |          ^

  Description:    unhandeled text.


 2. SyntaxError: No visibility specified. Did you intend to add "public"?
  --> contracts/tokens/IceToken.sol:37:5:
   |
37 |     function setTransferTax(uint256 dTransferTax_)
   |     ^ (Relevant source part starts here and spans across multiple lines).


Description: icetToken > To fix the error, we need to add the visibility specifier "public" to the function declaration at line 37.


## Contract Tests  (RED ZONE)

Controller test

    ✔ Should deploy tokens to holder (1570ms)
    ✔ Should have only listed admins (38ms)
    ✔ Should not set tokens again (62ms)
    ✔ Should not let non-owner set tokens or pause (43ms)
    ✔ Should claim rewards via controller (90ms)
    ✔ Should not allow users to claim rewards directly from tokens (132ms)
    ✔ Should not claim rewards when paused (50ms)
    ✔ Should swap H2O for Ice in virtual pool (90ms)
    ✔ Should swap Ice for H2O in virtual pool (79ms)
    ✔ Should not swap when paused and swap when unpaused (151ms)
    ✔ Should let owner set melt rate
    ✔ Should not let non-owner set melt rate
    ✔ Should let owner set error update period
    ✔ Should not let non-owner set melt rate
    ✔ Should get prices (ice swaps) (148ms)
    ✔ Should get prices (H2O swaps) (125ms)
    ✔ Should get pool sizes
    ✔ Should initiate positive auction (125ms)
    ✔ Should make valid positive auction bid (172ms)
    ✔ Should terminate positive auction at appropriate time (118ms)
    ✔ Should make positive auction bid and close (164ms)
    ✔ Should initiate negative auction (128ms)
    ✔ Should make valid negative auction bid (163ms)
    1) Should terminate negative auction at appropriate time
    2) Should make negative auction bid and close
    ✔ Should not auction when paused (84ms)
    ✔ Should not initiate auctions under improper conditions (121ms)
    ✔ Should not initiate auctions when already active (141ms)
    ✔ Should not initiate negative auction with insufficient contract ETH (101ms)
    ✔ Should not make bids or terminate auction when not active (45ms)
    ✔ Should mint ice cubes (75ms)
    ✔ Should redeem ice cube (99ms)
    ✔ Should preview ice cube rewards (85ms)
    ✔ Should claim ice cube rewards (124ms)
    ✔ Should claim partial ice cube rewards (126ms)
    ✔ Should not mint or redeem when paused (58ms)
    ✔ Should not claim cube rewards when paused (48ms)
    ✔ Should not let non-redeemer redeem (75ms)
    ✔ Should not let non-owner claim ice cube rewards (76ms)
    ✔ Exercise ctwon bug ICE->H2O magnitude (119ms)
    ✔ Exercise ctwon bug H2O->ICE directional (163ms)
    ✔ Exercise Meriadoc ETH revert attack (82ms)

  H2O Ice Virtual Pool test
    ✔ Should swapAB (347ms)
    ✔ Should swapBA (89ms)
    ✔ Should not swap for non-owner (49ms)
    ✔ Should not swap after deadline (45ms)
    ✔ Should not swap less than min amount (65ms)
    ✔ Should scale pools (48ms)
    ✔ Should not scale pools for non-owner
    ✔ Should not give tokens to unauthorized address

  H2O test
    ✔ Should mint h2o (126ms)
    ✔ Should burn h2o
    ✔ Should not mint or burn when paused (49ms)
    ✔ Should not let unauthorized address mint or burn (74ms)
    ✔ Should transfer
    ✔ Should not transfer when paused (39ms)
    ✔ Should not let non-admin pause or unpause (76ms)
    ✔ Should get decimals

  Ice Cube test
    ✔ Should mint ice cube (143ms)
    ✔ Should redeem ice cube (72ms)
    ✔ Should not mint or redeem when paused (74ms)
    ✔ Should not let unauthorized address mint or redeem (117ms)
    ✔ Should not redeem non-existent ice cube
    ✔ Should not redeem already redeemed ice cube (72ms)
    ✔ Should not redeem active ice cube (54ms)
    ✔ Should get ice cube creator balance (133ms)
    ✔ Should claim reward (73ms)
    ✔ Should not claim reward when paused (63ms)
    ✔ Should not claim reward on non-existent ice cube
    ✔ Should not let unauthorized address claim reward (72ms)
    ✔ Should transfer (87ms)
    ✔ Should not transfer when paused (77ms)
    ✔ Should not let non-admin pause or unpause (95ms)
    ✔ Should set approved (101ms)
    ✔ Should correctly indicate supported interfaces
    ✔ Should not return invalid getters

  Ice test
    ✔ Should mint ice (158ms)
    ✔ Should burn ice
    ✔ Should not mint or burn when paused
    ✔ Should not let unauthorized address mint or burn (82ms)
    ✔ Should claim reward
    ✔ Should not claim reward when paused
    ✔ Should not let unauthorized address claim reward (39ms)
    ✔ Should transfer (39ms)
    ✔ Should not transfer when paused
    ✔ Should not transfer when non-transferable but mint and burn (69ms)
    ✔ Should set transfer tax and apply it (51ms)
    3) Should not let unauthorized address set tax or transfer
    ✔ Should not let non-admin pause or unpause (73ms)
    ✔ Should get decimals

  Upgradeable Controller test
    ✔ Should deploy tokens to holder (814ms)
    ✔ Should have only listed admins
    ✔ Should not set tokens again
    ✔ Should claim rewards via controller (49ms)
    ✔ Should not allow users to claim rewards directly from tokens (73ms)
    ✔ Should swap H2O for Ice in virtual pool (72ms)
    ✔ Should swap Ice for H2O in virtual pool (74ms)
    ✔ Should not swap when paused and swap when unpaused (124ms)
    ✔ Should let owner set melt rate
    ✔ Should not let non-owner set melt rate
    ✔ Should let owner set error update period
    ✔ Should not let non-owner set melt rate

  Upgradeable Tokens test
    ✔ Should deploy tokens to holder (355ms)
    ✔ Should upgrade H2O to V2 (112ms)
    ✔ Should upgrade H2O to V3 (102ms)
    ✔ Should fail upgrading H2O to V4

  ETH Virtual Pool test
    ✔ Should swapAB (203ms)
    ✔ Should swapBA (92ms)

  Virtual Pool test
    ✔ Should swapAB (138ms)
    ✔ Should swapBA (111ms)
    ✔ Should not swap for non-owner (54ms)
    ✔ Should not swap after deadline
    ✔ Should not swap less than min amount
    ✔ Should scale pools (56ms)
    ✔ Should not scale pools for non-owner


  112 passing (12s)
  3 failing

  1) Controller test
       Should terminate negative auction at appropriate time:

      AssertionError: expected true to equal false
      + expected - actual

      -true
      +false

      at Context.<anonymous> (test\controllerTest.js:450:63)
      at processTicksAndRejections (node:internal/process/task_queues:95:5)
      at runNextTicks (node:internal/process/task_queues:64:3)
      at listOnTimeout (node:internal/timers:540:9)
      at processTimers (node:internal/timers:514:7)

  2) Controller test
       Should make negative auction bid and close:

      AssertionError: expected true to equal false
      + expected - actual

      -true
      +false

      at Context.<anonymous> (test\controllerTest.js:482:63)
      at processTicksAndRejections (node:internal/process/task_queues:95:5)
      at runNextTicks (node:internal/process/task_queues:64:3)
      at listOnTimeout (node:internal/timers:540:9)
      at processTimers (node:internal/timers:514:7)

  3) Ice test
       Should not let unauthorized address set tax or transfer:

      AssertionError: Expected transaction to be reverted
      + expected - actual

      -Transaction NOT reverted.
      +Transaction reverted.

      error Command failed with exit code 3


## Security test 

MockETHRevertAttack.submitBid() (contracts/mock/MockETHRevertAttack.sol#20-23) sends eth to arbitrary user
        Dangerous calls:
        - victim.initiatePositiveAuction{value: bidValue}() (contracts/mock/MockETHRevertAttack.sol#22)
MockEthVirtualPool._giveA(address,uint256) (contracts/mock/MockEthVirtualPool.sol#51-57) sends eth to arbitrary user
        Dangerous calls:
        - (success,None) = to.call{value: amount}() (contracts/mock/MockEthVirtualPool.sol#55)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#functions-that-send-ether-to-arbitrary-destinations
INFO:Detectors:
ERC1967UpgradeUpgradeable._functionDelegateCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#198-204) uses delegatecall to a input-controlled function id
        - (success,returndata) = target.delegatecall(data) (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#202)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#controlled-delegatecall
INFO:Detectors:
Distribution.distribute(address,address[],uint256) (contracts/Distribution.sol#12-24) ignores return value by token.transferFrom(msg.sender,addresses[i],amount) (contracts/Distribution.sol#22)
Distribution.distributeAmount(address,address[],uint256) (contracts/Distribution.sol#26-37) ignores return value by token.transferFrom(msg.sender,addresses[i],amount) (contracts/Distribution.sol#34)
Distribution.distributeAmounts(address,address[],uint256[]) (contracts/Distribution.sol#39-56) ignores return value by token.transferFrom(msg.sender,addresses[i],amounts[i]) (contracts/Distribution.sol#53)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#unchecked-transfer
INFO:Detectors:
H2OIceVirtualPool (contracts/H2OIceVirtualPool.sol#16-67) is an upgradeable contract that does not protect its initialize functions: H2OIceVirtualPool.initialize(H2OToken,IceToken,address) (contracts/H2OIceVirtualPool.sol#21-36). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)MockController_v2 (contracts/mock/MockController_v2.sol#6-16) is an upgradeable contract that does not protect its initialize functions: Controller.initialize() (contracts/Controller.sol#102-121). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)MockEthVirtualPool (contracts/mock/MockEthVirtualPool.sol#8-64) is an upgradeable contract that does not protect its initialize functions: MockEthVirtualPool.initialize(uint256,uint256) (contracts/mock/MockEthVirtualPool.sol#13-22). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)MockH2OToken_v2 (contracts/mock/MockH2OToken_v2.sol#6-18) is an upgradeable contract that does not protect its initialize functions: H2OToken.initialize(address[],address) (contracts/tokens/H2OToken.sol#15-20). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)MockH2OToken_v4 (contracts/mock/MockH2OToken_v4.sol#6-11) is an upgradeable contract that does not protect its initialize functions: H2OToken.initialize(address[],address) (contracts/tokens/H2OToken.sol#15-20). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)MockSimpleVirtualPool (contracts/mock/MockSimpleVirtualPool.sol#8-37) is an upgradeable contract that does not protect its initialize functions: MockSimpleVirtualPool.initialize(uint256,uint256) (contracts/mock/MockSimpleVirtualPool.sol#11-18). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)IceCube (contracts/tokens/IceCube.sol#10-217) is an upgradeable contract that does not protect its initialize functions: IceCube.initialize(address[]) (contracts/tokens/IceCube.sol#48-52). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)IceToken (contracts/tokens/IceToken.sol#10-80) is an upgradeable contract that does not protect its initialize functions: IceToken.initialize(address[],address) (contracts/tokens/IceToken.sol#22-31). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)SteamToken (contracts/tokens/SteamToken.sol#8-24) is an upgradeable contract that does not protect its initialize functions: SteamToken.initialize(address[],address) (contracts/tokens/SteamToken.sol#14-21). Anyone can delete the contract with: UUPSUpgradeable.upgradeTo(address) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#72-75)UUPSUpgradeable.upgradeToAndCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#85-88)Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#unprotected-upgradeable-contract
INFO:Detectors:
Controller._updateTargetSupply() (contracts/Controller.sol#559-638) uses a dangerous strict equality:
        - iTimeDelta == 0 (contracts/Controller.sol#567)
ERC20Reward._reward(address) (contracts/abstract/ERC20Reward.sol#59-75) uses a dangerous strict equality:
        - _iLastRewardTimes[account] == 0 (contracts/abstract/ERC20Reward.sol#60)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#dangerous-strict-equalities
INFO:Detectors:
Reentrancy in Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842):
        External calls:
        - h2oToken.burn(msg.sender,_H2OAmount + dTmpAmount) (contracts/Controller.sol#832)
        - h2oToken.mint(leadingBidder,dTmpAmount) (contracts/Controller.sol#833)
        State variables written after the call(s):
        - dLeadingBid = _ETHAmount (contracts/Controller.sol#835)
        Controller.dLeadingBid (contracts/Controller.sol#77) can be used in cross function reentrancies:
        - Controller._closeNegativeAuction() (contracts/Controller.sol#866-872)
        - Controller._closePositiveAuction() (contracts/Controller.sol#745-750)
        - Controller.dLeadingBid (contracts/Controller.sol#77)
        - Controller.initiateNegativeAuction(uint256,uint256) (contracts/Controller.sol#762-797)
        - Controller.initiatePositiveAuction() (contracts/Controller.sol#673-691)
        - Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842)
        - Controller.makePositiveAuctionBid() (contracts/Controller.sol#698-721)
        - leadingBidder = msg.sender (contracts/Controller.sol#834)
        Controller.leadingBidder (contracts/Controller.sol#74) can be used in cross function reentrancies:
        - Controller._closeNegativeAuction() (contracts/Controller.sol#866-872)
        - Controller._closePositiveAuction() (contracts/Controller.sol#745-750)
        - Controller.initiateNegativeAuction(uint256,uint256) (contracts/Controller.sol#762-797)
        - Controller.initiatePositiveAuction() (contracts/Controller.sol#673-691)
        - Controller.leadingBidder (contracts/Controller.sol#74)
        - Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842)
        - Controller.makePositiveAuctionBid() (contracts/Controller.sol#698-721)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-1
INFO:Detectors:
AccessControlEnumerableUpgradeable._grantRole(bytes32,address) (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#58-61) ignores return value by _roleMembers[role].add(account) (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#60)       
AccessControlEnumerableUpgradeable._revokeRole(bytes32,address) (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#66-69) ignores return value by _roleMembers[role].remove(account) (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#68)   
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#unused-return
INFO:Detectors:
ERC20Base.__ERC20Base_init(string,string,address[]).name (contracts/abstract/ERC20Base.sol#16) shadows:
        - ERC20Upgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#67-69) (function)
        - IERC20MetadataUpgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#17) (function)    
ERC20Base.__ERC20Base_init(string,string,address[]).symbol (contracts/abstract/ERC20Base.sol#17) shadows:
        - ERC20Upgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#75-77) (function)
        - IERC20MetadataUpgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#22) (function)  
ERC20MintableBurnable.__ERC20MintableBurnable_init(string,string,address[]).name (contracts/abstract/ERC20MintableBurnable.sol#19) shadows:
        - ERC20Upgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#67-69) (function)
        - IERC20MetadataUpgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#17) (function)    
ERC20MintableBurnable.__ERC20MintableBurnable_init(string,string,address[]).symbol (contracts/abstract/ERC20MintableBurnable.sol#20) shadows:
        - ERC20Upgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#75-77) (function)
        - IERC20MetadataUpgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#22) (function)  
ERC20Reward.__ERC20Reward_init(string,string,address[],uint256).name (contracts/abstract/ERC20Reward.sol#46) shadows:
        - ERC20Upgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#67-69) (function)
        - IERC20MetadataUpgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#17) (function)    
ERC20Reward.__ERC20Reward_init(string,string,address[],uint256).symbol (contracts/abstract/ERC20Reward.sol#47) shadows:
        - ERC20Upgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#75-77) (function)
        - IERC20MetadataUpgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#22) (function)  
ERC721Base.__ERC721Base_init(string,string,address[]).name (contracts/abstract/ERC721Base.sol#16) shadows:
        - ERC721Upgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#84-86) (function)
        - IERC721MetadataUpgradeable.name() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721MetadataUpgradeable.sol#16) (function) 
ERC721Base.__ERC721Base_init(string,string,address[]).symbol (contracts/abstract/ERC721Base.sol#17) shadows:
        - ERC721Upgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#91-93) (function)
        - IERC721MetadataUpgradeable.symbol() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721MetadataUpgradeable.sol#21) (function)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#local-variable-shadowing
INFO:Detectors:
VirtualPool.swapAB(address,uint256,uint256,uint256) (contracts/abstract/VirtualPool.sol#158-183) should emit an event for:
        - poolSizeA += dAmountA (contracts/abstract/VirtualPool.sol#175)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#missing-events-arithmetic
INFO:Detectors:
Distribution.distribute(address,address[],uint256) (contracts/Distribution.sol#12-24) has external calls inside a loop: token.transferFrom(msg.sender,addresses[i],amount) (contracts/Distribution.sol#22)
Distribution.distributeAmount(address,address[],uint256) (contracts/Distribution.sol#26-37) has external calls inside a loop: token.transferFrom(msg.sender,addresses[i],amount) (contracts/Distribution.sol#34)
Distribution.distributeAmounts(address,address[],uint256[]) (contracts/Distribution.sol#39-56) has external calls inside a loop: token.transferFrom(msg.sender,addresses[i],amounts[i]) (contracts/Distribution.sol#53)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation/#calls-inside-a-loop
INFO:Detectors:
Reentrancy in IceCube.mint(address,address,uint256,uint256,uint256) (contracts/tokens/IceCube.sol#170-192):
        External calls:
        - _safeMint(recipient,id) (contracts/tokens/IceCube.sol#183)
                - retval = IERC721ReceiverUpgradeable(to).onERC721Received(_msgSender(),from,tokenId,data) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#406-417)
        State variables written after the call(s):
        - _creatorBalances[creator].push(id) (contracts/tokens/IceCube.sol#189)
        - params[id] = Params(false,amount,startTime,endTime,startTime,creator) (contracts/tokens/IceCube.sol#186-187)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-2
INFO:Detectors:
Reentrancy in Controller._closeNegativeAuction() (contracts/Controller.sol#866-872):
        External calls:
        - sendETH(leadingBidder,dLeadingBid,) (contracts/Controller.sol#869)
                - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
        Event emitted after the call(s):
        - CloseAuction(leadingBidder,false,dLeadingBid,dAuctionH2OAmount) (contracts/Controller.sol#871)
Reentrancy in Controller._closePositiveAuction() (contracts/Controller.sol#745-750):
        External calls:
        - h2oToken.mint(leadingBidder,dAuctionH2OAmount) (contracts/Controller.sol#747)
        Event emitted after the call(s):
        - CloseAuction(leadingBidder,true,dLeadingBid,dAuctionH2OAmount) (contracts/Controller.sol#749)
Reentrancy in Controller.claimRewards() (contracts/Controller.sol#470-486):
        External calls:
        - dAmount = iceToken.claimReward(msg.sender).mul(dMeltRate) (contracts/Controller.sol#474)
        - h2oToken.mint(msg.sender,dAmount) (contracts/Controller.sol#477)
        - icePool.scalePools(dScaleRatio) (contracts/Controller.sol#481)
        Event emitted after the call(s):
        - ClaimRewards(msg.sender,dAmount) (contracts/Controller.sol#483)
Reentrancy in Controller.claimRewardsFromCube(uint256) (contracts/Controller.sol#524-551):
        External calls:
        - iceCube.claimRewards(tokenId) (contracts/Controller.sol#533)
        - h2oToken.mint(msg.sender,dAmount) (contracts/Controller.sol#536)
        - _redeemIceCube(tokenId) (contracts/Controller.sol#541)
                - iceCube.redeem(tokenId) (contracts/Controller.sol#442)
                - iceToken.mint(iceCube.getRedeemer(tokenId),dAmount) (contracts/Controller.sol#443)
        - icePool.scalePools(dScaleRatio) (contracts/Controller.sol#546)
        Event emitted after the call(s):
        - ClaimRewardsFromCube(msg.sender,tokenId,dAmount) (contracts/Controller.sol#548)
Reentrancy in Controller.initiateNegativeAuction(uint256,uint256) (contracts/Controller.sol#762-797):
        External calls:
        - h2oToken.burn(msg.sender,_H2OAmount) (contracts/Controller.sol#793)
        Event emitted after the call(s):
        - InitiateAuction(msg.sender,false,_ETHAmount,_H2OAmount,block.timestamp) (contracts/Controller.sol#795-796)
Reentrancy in Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842):
        External calls:
        - h2oToken.burn(msg.sender,_H2OAmount + dTmpAmount) (contracts/Controller.sol#832)
        - h2oToken.mint(leadingBidder,dTmpAmount) (contracts/Controller.sol#833)
        - _closeNegativeAuction() (contracts/Controller.sol#838)
                - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
        External calls sending eth:
        - _closeNegativeAuction() (contracts/Controller.sol#838)
                - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
        Event emitted after the call(s):
        - AuctionBid(msg.sender,false,_ETHAmount) (contracts/Controller.sol#841)
        - CloseAuction(leadingBidder,false,dLeadingBid,dAuctionH2OAmount) (contracts/Controller.sol#871)
                - _closeNegativeAuction() (contracts/Controller.sol#838)
Reentrancy in Controller.makePositiveAuctionBid() (contracts/Controller.sol#698-721):
        External calls:
        - _closePositiveAuction() (contracts/Controller.sol#714)
                - h2oToken.mint(leadingBidder,dAuctionH2OAmount) (contracts/Controller.sol#747)
        - sendETH(previousLeadingBidder,dPreviousLeadingBid,) (contracts/Controller.sol#718)
                - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
        External calls sending eth:
        - sendETH(previousLeadingBidder,dPreviousLeadingBid,) (contracts/Controller.sol#718)
                - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
        Event emitted after the call(s):
        - AuctionBid(msg.sender,true,msg.value) (contracts/Controller.sol#720)
Reentrancy in Controller.mintIceCube(uint256,address,uint256) (contracts/Controller.sol#406-419):
        External calls:
        - iceToken.burn(msg.sender,amount) (contracts/Controller.sol#412)
        - tokenId = iceCube.mint(msg.sender,recipient,amount,block.timestamp,endTime) (contracts/Controller.sol#413-414)
        Event emitted after the call(s):
        - MintCube(msg.sender,recipient,amount,endTime,tokenId) (contracts/Controller.sol#416)
Reentrancy in Controller.redeemIceCube(uint256) (contracts/Controller.sol#426-433):
        External calls:
        - dAmount = _redeemIceCube(tokenId) (contracts/Controller.sol#430)
                - iceCube.redeem(tokenId) (contracts/Controller.sol#442)
                - iceToken.mint(iceCube.getRedeemer(tokenId),dAmount) (contracts/Controller.sol#443)
        Event emitted after the call(s):
        - RedeemCube(msg.sender,tokenId,dAmount) (contracts/Controller.sol#431)
Reentrancy in Controller.swapH2OForICE(uint256,uint256,uint256) (contracts/Controller.sol#340-362):
        External calls:
        - dICEAmount = icePool.swapAB(_msgSender(),dH2OAmount,dMinICEAmount,deadline) (contracts/Controller.sol#350-354)
        Event emitted after the call(s):
        - Swap(msg.sender,address(h2oToken),dH2OAmount,address(iceToken),dICEAmount) (contracts/Controller.sol#356-359)
Reentrancy in Controller.swapICEForH2O(uint256,uint256,uint256) (contracts/Controller.sol#374-395):
        External calls:
        - dH2OAmount = icePool.swapBA(_msgSender(),dICEAmount,dMinH2OAmount,deadline) (contracts/Controller.sol#383-387)
        Event emitted after the call(s):
        - Swap(msg.sender,address(iceToken),dICEAmount,address(h2oToken),dH2OAmount) (contracts/Controller.sol#389-392)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-3
INFO:Detectors:
Controller.claimRewardsFromCube(uint256) (contracts/Controller.sol#524-551) uses timestamp for comparisons
        Dangerous comparisons:
        - block.timestamp >= iEndTime && iceCube.isRedeemed(tokenId) == false (contracts/Controller.sol#539-540)
Controller._updateTargetSupply() (contracts/Controller.sol#559-638) uses timestamp for comparisons
        Dangerous comparisons:
        - iTimeDelta == 0 (contracts/Controller.sol#567)
        - block.timestamp >= iNextUpdateTime (contracts/Controller.sol#594)
Controller.makePositiveAuctionBid() (contracts/Controller.sol#698-721) uses timestamp for comparisons
        Dangerous comparisons:
        - block.timestamp > (iLastAuctionTime + I_DEFAULT_AUCTION_PERIOD) (contracts/Controller.sol#713)
Controller.terminatePositiveAuction() (contracts/Controller.sol#728-737) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(block.timestamp > (iLastAuctionTime + I_DEFAULT_AUCTION_PERIOD),There is still time remaining in the Auction.) (contracts/Controller.sol#734-735)
Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842) uses timestamp for comparisons
        Dangerous comparisons:
        - block.timestamp > (iLastAuctionTime + I_DEFAULT_AUCTION_PERIOD) (contracts/Controller.sol#837)
Controller.terminateNegativeAuction() (contracts/Controller.sol#850-858) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(block.timestamp > (iLastAuctionTime + I_DEFAULT_AUCTION_PERIOD),There is still time remaining in the Auction) (contracts/Controller.sol#855-856)
ERC20Reward._reward(address) (contracts/abstract/ERC20Reward.sol#59-75) uses timestamp for comparisons
        Dangerous comparisons:
        - _iLastRewardTimes[account] == 0 (contracts/abstract/ERC20Reward.sol#60)
VirtualPool.swapAB(address,uint256,uint256,uint256) (contracts/abstract/VirtualPool.sol#158-183) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(deadline > block.timestamp,Deadline Expired) (contracts/abstract/VirtualPool.sol#165)
VirtualPool.swapBA(address,uint256,uint256,uint256) (contracts/abstract/VirtualPool.sol#205-229) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(deadline > block.timestamp,Deadline Expired) (contracts/abstract/VirtualPool.sol#212)
IceCube.redeem(uint256) (contracts/tokens/IceCube.sol#209-216) uses timestamp for comparisons
        Dangerous comparisons:
        - require(bool,string)(block.timestamp > params[id].endTime,Cannot redeem an active Ice Cube.) (contracts/tokens/IceCube.sol#214)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#block-timestamp
INFO:Detectors:
ERC721Upgradeable._checkOnERC721Received(address,address,uint256,bytes) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#399-421) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#413-415)
AddressUpgradeable.verifyCallResult(bool,bytes,string) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#174-194) uses assembly        
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#186-189)
StorageSlotUpgradeable.getAddressSlot(bytes32) (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#52-57) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#54-56)
StorageSlotUpgradeable.getBooleanSlot(bytes32) (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#62-67) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#64-66)
StorageSlotUpgradeable.getBytes32Slot(bytes32) (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#72-77) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#74-76)
StorageSlotUpgradeable.getUint256Slot(bytes32) (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#82-87) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#84-86)
EnumerableSetUpgradeable.values(EnumerableSetUpgradeable.AddressSet) (node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#282-292) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#287-289)
EnumerableSetUpgradeable.values(EnumerableSetUpgradeable.UintSet) (node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#356-366) uses assembly
        - INLINE ASM (node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#361-363)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#assembly-usage
INFO:Detectors:
Controller.claimRewardsFromCube(uint256) (contracts/Controller.sol#524-551) compares to a boolean constant:
        -block.timestamp >= iEndTime && iceCube.isRedeemed(tokenId) == false (contracts/Controller.sol#539-540)
Controller.makePositiveAuctionBid() (contracts/Controller.sol#698-721) compares to a boolean constant:
        -require(bool,string)(isPositiveAuctionActive == true,There is no active auction.) (contracts/Controller.sol#704-705)
Controller.terminatePositiveAuction() (contracts/Controller.sol#728-737) compares to a boolean constant:
        -require(bool,string)(isPositiveAuctionActive == true,There is no active auction.) (contracts/Controller.sol#730)
Controller.initiateNegativeAuction(uint256,uint256) (contracts/Controller.sol#762-797) compares to a boolean constant:
        -require(bool,string)(isPositiveAuctionActive == false && isNegativeAuctionActive == false,There is already an active auction.) (contracts/Controller.sol#778-780)
Controller.makeNegativeAuctionBid(uint256,uint256) (contracts/Controller.sol#809-842) compares to a boolean constant:
        -require(bool,string)(isNegativeAuctionActive == true,There is no active auction.) (contracts/Controller.sol#816-817)
Controller.terminateNegativeAuction() (contracts/Controller.sol#850-858) compares to a boolean constant:
        -require(bool,string)(isNegativeAuctionActive == true,There is no active auction.) (contracts/Controller.sol#851)
Controller._closeNegativeAuction() (contracts/Controller.sol#866-872) compares to a boolean constant:
        -isNegativeAuctionActive != false (contracts/Controller.sol#867)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#boolean-equality
INFO:Detectors:
3 different versions of Solidity are used:
        - Version constraint ^0.8.0 is used by:
                - node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/access/IAccessControlEnumerableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/access/IAccessControlUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/interfaces/draft-IERC1822Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/proxy/beacon/IBeaconUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/IERC721ReceiverUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/IERC721Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/ERC721EnumerableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721EnumerableUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721MetadataUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/StringsUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/IERC165Upgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts/token/ERC20/ERC20.sol#4
                - node_modules/@openzeppelin/contracts/token/ERC20/IERC20.sol#4
                - node_modules/@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol#4
                - node_modules/@openzeppelin/contracts/utils/Context.sol#4
                - node_modules/@openzeppelin/contracts/utils/Counters.sol#4
                - contracts/Constants.sol#2
                - contracts/Controller.sol#2
                - contracts/Distribution.sol#2
                - contracts/H2OIceVirtualPool.sol#2
                - contracts/abstract/ERC20Base.sol#2
                - contracts/abstract/ERC20MintableBurnable.sol#2
                - contracts/abstract/ERC20Reward.sol#2
                - contracts/abstract/ERC721Base.sol#2
                - contracts/abstract/ERCTokenBase.sol#2
                - contracts/abstract/VirtualPool.sol#2
                - contracts/lib/FixedPoint.sol#3
                - contracts/mock/MockController_v2.sol#2
                - contracts/mock/MockERC20MintableBurnable_v3.sol#2
                - contracts/mock/MockETHRevertAttack.sol#2
                - contracts/mock/MockEthVirtualPool.sol#2
                - contracts/mock/MockH2OToken_v2.sol#2
                - contracts/mock/MockH2OToken_v3.sol#2
                - contracts/mock/MockH2OToken_v4.sol#2
                - contracts/mock/MockSimpleVirtualPool.sol#2
                - contracts/tokens/H2OToken.sol#2
                - contracts/tokens/IceCube.sol#2
                - contracts/tokens/IceToken.sol#2
                - contracts/tokens/SteamToken.sol#2
        - Version constraint ^0.8.2 is used by:
                - node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#4
                - node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol#4
        - Version constraint ^0.8.1 is used by:
                - node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#4
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#different-pragma-directives-are-used
INFO:Detectors:
SFixedPoint.toDecimal(int256) (contracts/lib/FixedPoint.sol#103-105) is never used and should be removed
SFixedPoint.toInteger(int256) (contracts/lib/FixedPoint.sol#112-114) is never used and should be removed
UFixedPoint.toDecimal(uint256) (contracts/lib/FixedPoint.sol#39-41) is never used and should be removed
UFixedPoint.toInteger(uint256) (contracts/lib/FixedPoint.sol#48-50) is never used and should be removed
max(uint256,uint256) (contracts/lib/FixedPoint.sol#60-63) is never used and should be removed
min(int256,int256) (contracts/lib/FixedPoint.sol#134-137) is never used and should be removed
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#dead-code
INFO:Detectors:
Version constraint ^0.8.0 contains known severe issues (https://solidity.readthedocs.io/en/latest/bugs.html)
        - FullInlinerNonExpressionSplitArgumentEvaluationOrder
        - MissingSideEffectsOnSelectorAccess
        - AbiReencodingHeadOverflowWithStaticArrayCleanup
        - DirtyBytesArrayToStorage
        - DataLocationChangeInInternalOverride
        - NestedCalldataArrayAbiReencodingSizeValidation
        - SignedImmutables
        - ABIDecodeTwoDimensionalArrayMemory
        - KeccakCaching.
 It is used by:
        - node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/access/IAccessControlEnumerableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/access/IAccessControlUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/interfaces/draft-IERC1822Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/proxy/beacon/IBeaconUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/IERC20Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/extensions/IERC20MetadataUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/IERC721ReceiverUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/IERC721Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/ERC721EnumerableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721EnumerableUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/IERC721MetadataUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/StorageSlotUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/StringsUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/IERC165Upgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/utils/structs/EnumerableSetUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts/token/ERC20/ERC20.sol#4
        - node_modules/@openzeppelin/contracts/token/ERC20/IERC20.sol#4
        - node_modules/@openzeppelin/contracts/token/ERC20/extensions/IERC20Metadata.sol#4
        - node_modules/@openzeppelin/contracts/utils/Context.sol#4
        - node_modules/@openzeppelin/contracts/utils/Counters.sol#4
        - contracts/Constants.sol#2
        - contracts/Controller.sol#2
        - contracts/Distribution.sol#2
        - contracts/H2OIceVirtualPool.sol#2
        - contracts/abstract/ERC20Base.sol#2
        - contracts/abstract/ERC20MintableBurnable.sol#2
        - contracts/abstract/ERC20Reward.sol#2
        - contracts/abstract/ERC721Base.sol#2
        - contracts/abstract/ERCTokenBase.sol#2
        - contracts/abstract/VirtualPool.sol#2
        - contracts/lib/FixedPoint.sol#3
        - contracts/mock/MockController_v2.sol#2
        - contracts/mock/MockERC20MintableBurnable_v3.sol#2
        - contracts/mock/MockETHRevertAttack.sol#2
        - contracts/mock/MockEthVirtualPool.sol#2
        - contracts/mock/MockH2OToken_v2.sol#2
        - contracts/mock/MockH2OToken_v3.sol#2
        - contracts/mock/MockH2OToken_v4.sol#2
        - contracts/mock/MockSimpleVirtualPool.sol#2
        - contracts/tokens/H2OToken.sol#2
        - contracts/tokens/IceCube.sol#2
        - contracts/tokens/IceToken.sol#2
        - contracts/tokens/SteamToken.sol#2
Version constraint ^0.8.2 contains known severe issues (https://solidity.readthedocs.io/en/latest/bugs.html)
        - FullInlinerNonExpressionSplitArgumentEvaluationOrder
        - MissingSideEffectsOnSelectorAccess
        - AbiReencodingHeadOverflowWithStaticArrayCleanup
        - DirtyBytesArrayToStorage
        - DataLocationChangeInInternalOverride
        - NestedCalldataArrayAbiReencodingSizeValidation
        - SignedImmutables
        - ABIDecodeTwoDimensionalArrayMemory
        - KeccakCaching.
 It is used by:
        - node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#4
        - node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol#4
Version constraint ^0.8.1 contains known severe issues (https://solidity.readthedocs.io/en/latest/bugs.html)
        - FullInlinerNonExpressionSplitArgumentEvaluationOrder
        - MissingSideEffectsOnSelectorAccess
        - AbiReencodingHeadOverflowWithStaticArrayCleanup
        - DirtyBytesArrayToStorage
        - DataLocationChangeInInternalOverride
        - NestedCalldataArrayAbiReencodingSizeValidation
        - SignedImmutables
        - ABIDecodeTwoDimensionalArrayMemory
        - KeccakCaching.
 It is used by:
        - node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#4
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity
INFO:Detectors:
Low level call in ERC1967UpgradeUpgradeable._functionDelegateCall(address,bytes) (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#198-204):
        - (success,returndata) = target.delegatecall(data) (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#202)       
Low level call in AddressUpgradeable.sendValue(address,uint256) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#60-65):
        - (success,None) = recipient.call{value: amount}() (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#63)
Low level call in AddressUpgradeable.functionCallWithValue(address,bytes,uint256,string) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#128-139):
        - (success,returndata) = target.call{value: value}(data) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#137)
Low level call in AddressUpgradeable.functionStaticCall(address,bytes,string) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#157-166):
        - (success,returndata) = target.staticcall(data) (node_modules/@openzeppelin/contracts-upgradeable/utils/AddressUpgradeable.sol#164)
Low level call in Controller.sendETH(address,uint256,bytes) (contracts/Controller.sol#881-889):
        - (sent,None) = to.call{value: dETHAmount}(data) (contracts/Controller.sol#887)
Low level call in MockEthVirtualPool._giveA(address,uint256) (contracts/mock/MockEthVirtualPool.sol#51-57):
        - (success,None) = to.call{value: amount}() (contracts/mock/MockEthVirtualPool.sol#55)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#low-level-calls
INFO:Detectors:
Function AccessControlEnumerableUpgradeable.__AccessControlEnumerable_init() (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#15-16) is not in mixedCase
Function AccessControlEnumerableUpgradeable.__AccessControlEnumerable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#18-19) is not in mixedCase
Variable AccessControlEnumerableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlEnumerableUpgradeable.sol#76) is not in mixedCase
Function AccessControlUpgradeable.__AccessControl_init() (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol#51-52) is not in mixedCase
Function AccessControlUpgradeable.__AccessControl_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol#54-55) is not in mixedCase
Variable AccessControlUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/access/AccessControlUpgradeable.sol#259) is not in mixedCase
Function OwnableUpgradeable.__Ownable_init() (node_modules/@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol#29-31) is not in mixedCase
Function OwnableUpgradeable.__Ownable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol#33-35) is not in mixedCase   
Variable OwnableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/access/OwnableUpgradeable.sol#94) is not in mixedCase
Function ERC1967UpgradeUpgradeable.__ERC1967Upgrade_init() (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#21-22) is not in mixedCase
Function ERC1967UpgradeUpgradeable.__ERC1967Upgrade_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#24-25) is not in mixedCase
Variable ERC1967UpgradeUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/proxy/ERC1967/ERC1967UpgradeUpgradeable.sol#211) is not in mixedCase     
Function UUPSUpgradeable.__UUPSUpgradeable_init() (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#23-24) is not in mixedCase      
Function UUPSUpgradeable.__UUPSUpgradeable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#26-27) is not in mixedCase
Variable UUPSUpgradeable.__self (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#29) is not in mixedCase
Variable UUPSUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/proxy/utils/UUPSUpgradeable.sol#107) is not in mixedCase
Function PausableUpgradeable.__Pausable_init() (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#34-36) is not in mixedCase        
Function PausableUpgradeable.__Pausable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#38-40) is not in mixedCase
Variable PausableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/PausableUpgradeable.sol#116) is not in mixedCase
Function ReentrancyGuardUpgradeable.__ReentrancyGuard_init() (node_modules/@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol#40-42) is not in mixedCase
Function ReentrancyGuardUpgradeable.__ReentrancyGuard_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol#44-46) is not in mixedCase
Variable ReentrancyGuardUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/security/ReentrancyGuardUpgradeable.sol#74) is not in mixedCase
Function ERC20Upgradeable.__ERC20_init(string,string) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#55-57) is not in mixedCase 
Function ERC20Upgradeable.__ERC20_init_unchained(string,string) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#59-62) is not in mixedCase
Variable ERC20Upgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/token/ERC20/ERC20Upgradeable.sol#394) is not in mixedCase
Function ERC721Upgradeable.__ERC721_init(string,string) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#45-47) is not in mixedCase
Function ERC721Upgradeable.__ERC721_init_unchained(string,string) (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#49-52) is not in mixedCase
Variable ERC721Upgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/ERC721Upgradeable.sol#465) is not in mixedCase
Function ERC721EnumerableUpgradeable.__ERC721Enumerable_init() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/ERC721EnumerableUpgradeable.sol#16-17) is not in mixedCase
Function ERC721EnumerableUpgradeable.__ERC721Enumerable_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/ERC721EnumerableUpgradeable.sol#19-20) is not in mixedCase
Variable ERC721EnumerableUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/token/ERC721/extensions/ERC721EnumerableUpgradeable.sol#175) is not in mixedCase
Function ContextUpgradeable.__Context_init() (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#18-19) is not in mixedCase
Function ContextUpgradeable.__Context_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#21-22) is not in mixedCase    
Variable ContextUpgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/utils/ContextUpgradeable.sol#36) is not in mixedCase
Function ERC165Upgradeable.__ERC165_init() (node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol#24-25) is not in mixedCase   
Function ERC165Upgradeable.__ERC165_init_unchained() (node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol#27-28) is not in mixedCase
Variable ERC165Upgradeable.__gap (node_modules/@openzeppelin/contracts-upgradeable/utils/introspection/ERC165Upgradeable.sol#41) is not in mixedCase
Parameter Controller.initiateNegativeAuction(uint256,uint256)._H2OAmount (contracts/Controller.sol#763) is not in mixedCase
Parameter Controller.initiateNegativeAuction(uint256,uint256)._ETHAmount (contracts/Controller.sol#764) is not in mixedCase
Parameter Controller.makeNegativeAuctionBid(uint256,uint256)._H2OAmount (contracts/Controller.sol#810) is not in mixedCase
Parameter Controller.makeNegativeAuctionBid(uint256,uint256)._ETHAmount (contracts/Controller.sol#811) is not in mixedCase
Function ERC20Base.__ERC20Base_init(string,string,address[]) (contracts/abstract/ERC20Base.sol#15-24) is not in mixedCase
Variable ERC20Base.__gap (contracts/abstract/ERC20Base.sol#13) is not in mixedCase
Function ERC20MintableBurnable.__ERC20MintableBurnable_init(string,string,address[]) (contracts/abstract/ERC20MintableBurnable.sol#18-26) is not in mixedCase       
Variable ERC20MintableBurnable.__gap (contracts/abstract/ERC20MintableBurnable.sol#15) is not in mixedCase
Function ERC20Reward.__ERC20Reward_init(string,string,address[],uint256) (contracts/abstract/ERC20Reward.sol#45-55) is not in mixedCase
Variable ERC20Reward.D_REWARDS_DECAY_RATE (contracts/abstract/ERC20Reward.sol#39) is not in mixedCase
Variable ERC20Reward.__gap (contracts/abstract/ERC20Reward.sol#42) is not in mixedCase
Function ERC721Base.__ERC721Base_init(string,string,address[]) (contracts/abstract/ERC721Base.sol#15-25) is not in mixedCase
Variable ERC721Base.__gap (contracts/abstract/ERC721Base.sol#13) is not in mixedCase
Function ERCTokenBase.__ERCTokenBase_init(address[]) (contracts/abstract/ERCTokenBase.sol#19-30) is not in mixedCase
Variable ERCTokenBase.__gap (contracts/abstract/ERCTokenBase.sol#16) is not in mixedCase
Function VirtualPool.__VirtualPool_init(uint256,uint256) (contracts/abstract/VirtualPool.sol#39-51) is not in mixedCase
Contract MockController_v2 (contracts/mock/MockController_v2.sol#6-16) is not in CapWords
Contract MockERC20MintableBurnable_v3 (contracts/mock/MockERC20MintableBurnable_v3.sol#8-19) is not in CapWords
Variable MockERC20MintableBurnable_v3.__gap (contracts/mock/MockERC20MintableBurnable_v3.sol#17) is not in mixedCase
Contract MockH2OToken_v2 (contracts/mock/MockH2OToken_v2.sol#6-18) is not in CapWords
Contract MockH2OToken_v3 (contracts/mock/MockH2OToken_v3.sol#8-20) is not in CapWords
Contract MockH2OToken_v4 (contracts/mock/MockH2OToken_v4.sol#6-11) is not in CapWords
Variable IceToken.D_ICE_TRANSFER_TAX (contracts/tokens/IceToken.sol#16) is not in mixedCase
Variable IceToken.D_IS_ICE_TRANSFERABLE (contracts/tokens/IceToken.sol#17) is not in mixedCase
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#conformance-to-solidity-naming-conventions
INFO:Detectors:
Variable VirtualPool.swapBA(address,uint256,uint256,uint256).dMinAmountA (contracts/abstract/VirtualPool.sol#208) is too similar to VirtualPool.swapAB(address,uint256,uint256,uint256).dMinAmountB (contracts/abstract/VirtualPool.sol#161)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#variable-names-too-similar
INFO:Detectors:
The following unused import(s) in contracts/H2OIceVirtualPool.sol should be removed:
        -import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol"; (contracts/H2OIceVirtualPool.sol#4)
The following unused import(s) in contracts/mock/MockEthVirtualPool.sol should be removed:
        -import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol"; (contracts/mock/MockEthVirtualPool.sol#4)
The following unused import(s) in contracts/mock/MockSimpleVirtualPool.sol should be removed:
        -import "@openzeppelin/contracts-upgradeable/proxy/utils/Initializable.sol"; (contracts/mock/MockSimpleVirtualPool.sol#4)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#unused-imports
INFO:Detectors:
MockH2OToken_v3.newVar1 (contracts/mock/MockH2OToken_v3.sol#11) should be constant
MockH2OToken_v3.newVar2 (contracts/mock/MockH2OToken_v3.sol#12) should be constant
MockH2OToken_v4.newVar2 (contracts/mock/MockH2OToken_v4.sol#9) should be constant
MockH2OToken_v4.newVar3 (contracts/mock/MockH2OToken_v4.sol#8) should be constant
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#state-variables-that-could-be-declared-constant
INFO:Detectors:
MockETHRevertAttack.victim (contracts/mock/MockETHRevertAttack.sol#8) should be immutable
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#state-variables-that-could-be-declared-immutable
INFO:Slither:. analyzed (56 contracts with 95 detectors), 155 result(s) found

