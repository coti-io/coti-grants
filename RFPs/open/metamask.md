# COTI RFP - Metamask Integration


## Project Overview


### Background

COTI is a privacy preserving L2 on ethereum. It allows secure multi party computation using garbled circuits. Parties can jointly compute one or more functions over their inputs and keep the inputs private. Users can do MPC with encrypted data, never having to reveal sensitive information.

COTI native encryption poses a challenge for integrating with MetaMask, as MetaMask cannot natively read encrypted data on the COTI network.

To overcome this limitation, we are looking to develop a MetaMask Snap using MetaMask Flask. This Snap will enable users to read and manage their encrypted data on the COTI network through MetaMask, providing a seamless and secure user experience.


### Objectives



* Create MetaMask Snap to read and display encrypted balances on the COTI v2 network.
    * For example, an encrypted balance returns a value of 0. Once the snap is available, the actual balance of the account queried should be returned.
* Ensure secure communication and data integrity between COTI v2 and MetaMask.
* Maintain compatibility with existing MetaMask features and functionalities.


## Eligibility Criteria

_Before applying for this RFP, be sure you meet the criteria below._



* All applicants must be willing to undergo and be able to pass KYC/KYB. 
* Applicants must not be in an OFAC sanctioned jurisdiction or any similar watchlists


## Funding Details

_COTI grant program RFPs are bid-for-service and the Maximum Funding Amount isn’t indicative of the bid amount one should apply for but rather the cap that COTI puts on this particular Request for Proposal. In most cases, winning proposals are significantly less than the Maximum Funding Amount._


### Funding Type:

COTI offers grants for this RFP in the following: 

1. USD / Stablecoin
2. COTI Token
3. Either


### Funding structure: Select One



1. Milestone-based
* If milestone based then write milestones here along with:
    * Percentage of funding released per milestone [20% of Grant]
    * Amount of time given to complete each milestone

2. Lump sum
    1. Pre
    2. Post

3. Post Hoc


## Acceptance / Evaluation Criteria

_Projects awarded a grant will be checked on the following criterion before work is considered as complete, in full or partially._


### Functional Requirements



1. **MetaMask Snap Development**

    1. Develop a MetaMask Snap using MetaMask Flask to support COTI v2’s encryption scheme.

    2. Implement functionality within the Snap to decrypt and display COTI v2 contracts data.

    3. The snap must work with the following token types (so that when a user deploys an encrypted token, ONLY authorized users can view balances)
        1. ERC20
        2. ERC721
        3. ERC1155

    4. Ensure the Snap is secure and does not compromise user data.

    5. Follow [Metamask’s Snap design guidelines](https://docs.metamask.io/snaps/learn/best-practices/design-guidelines/)

2. **Authentication and Authorization**
    6. Method for authenticating COTI v2 accounts within the MetaMask Snap. This should be completed by either providing the user’s key to Metamask or by pointing Metamask to the contract that holds the key. This should work with existing Metamask functionality.

3. **Data Display and Management**
    7. Provide functionality to decrypt and display user data on the COTI v2 network within the MetaMask Snap. This should include the ability to decrypt any data, including  network  data and smart contract data, using the contracts' abi data
    8. Support sending and receiving transactions on the COTI v2 network through the MetaMask Snap. This includes querying contract states, sending transactions to modify the state, and calling contract functions.


### Non-Functional Requirements

1. **Security:** Ensure end-to-end encryption for all communications between MetaMask Flask and the COTI v2 network.

2. **Performance:** Optimize the Snap to ensure fast and efficient decryption of data.

3. **Scalability:** Design the Snap to support a large number of users and transactions.

4. **Support**: Provide support for any issues that arise from v1 for up to 12mo.


### Technical Requirements

1. **Development Environment**: Utilize COTI v2 SDKs for all network interactions where possible. Provide feedback to the COTI team on the usage of the SDK.

2. **Testing**: Implement comprehensive testing, including unit tests, integration tests, and user acceptance tests.

3. **Code and Documentation**: Provide final solution in a private GitHub repository. Provide clear documentation via README. Optionally, transfer repo to the COTI GitHub organization upon request.

## Deadlines & Dates

### RFP Submission/Response deadline:

_Proposals must be received by 23:59 UTC on the date provided._

2024-10-01


### RFP Award Announcement Date

_The COTI Foundation will notify successful applicants of their proposal acceptance by the date below._

TBD


### RFP Completion / Build Deadline 

_Successful applicants must complete the entire project or build by the date below._

2024-12-01


## Support / Follow Through Criteria

_For many projects, there is work that happens in the ecosystem, community, and with your users that continues well beyond general acceptance of the initial delivery. This may include bugs, review of new features contributed by the community, etc. We’ve stipulated below what support and follow through we expect as part of the full lifecycle of your proposal._

* 6mo defect support


## Contact Information

_If you have questions on this particular RFP, please contact using the content information below. _

[ADD CONTACT DETAILS HERE]


## Legal and Compliance

_All applicants must agree to the following additional legal and compliance concerns._

* All IP created as part of this grant will be developed under the Apache 2.0 license.

* Grantee agrees to transfer all assets created as part of this grant to the COTI Foundation.


## Other Notes

### Useful Links

* [Coti Docs](https://docs.coti.io)

* ECR20 Typescript example [https://github.com/coti-io/coti-sdk-typescript-examples/blob/main/deployments/ERC20Example.json](https://github.com/coti-io/coti-sdk-typescript-examples/blob/main/deployments/ERC20Example.json) 

* Confidentiality Contracts [https://github.com/coti-io/confidentiality-contracts](https://github.com/coti-io/confidentiality-contracts) 

    * GC Precomiles readme [https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/examples/precompiles/precompiles_readme.md](https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/examples/precompiles/precompiles_readme.md) 

    * MPC Core readme [https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/lib/lib_readme.md](https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/lib/lib_readme.md) 

* SDKs

    * [Python SDK](https://github.com/coti-io/coti-sdk-python)
    * [Typescript SDK](https://github.com/coti-io/coti-sdk-typescript)
    * [Hardhat](https://github.com/coti-io/confidentiality-contracts?tab=readme-ov-file#hardhat-confidential-contracts)

* Examples
    * [Python SDK Examples](https://github.com/coti-io/coti-sdk-python-examples)
    * [Typescript SDK Examples](https://github.com/coti-io/confidentiality-contracts?tab=readme-ov-file#hardhat-confidential-contracts:~:text=Typescript%20SDK%20Examples)
    
* Network
    * [Faucet](https://faucet.coti.io/)
    * [Explorer](https://explorer-devnet.coti.io/overview)