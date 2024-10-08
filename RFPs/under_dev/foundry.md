# COTI RFP - Foundry Toolkit


## Project Overview


### Background

COTI is a privacy preserving L2 on ethereum. It allows secure multi party computation using garbled circuits. Parties can jointly compute one or more functions over their inputs and keep the inputs private. Users can do MPC with encrypted data, never having to reveal sensitive information.

COTI introduces unique precompiles and methods that extend the EVM into the gcEVM (garbled-circuits EVM). As such, supporting these methods in an easy, familiar way is important for developers.


### Objectives

* Create a Foundry COTI Toolkit to allow developers to interact with COTI methods/functions atomically.

* Include the most important functionality for COTI developers using Foundry extension methods

* Design and implement in an extensible manner to allow for future development. Architecture and documentation should allow multiple parties to contribute to the future development/additions for the COTI plugin.


## Eligibility Criteria

_Before applying for this RFP, be sure you meet the criteria below._

* All applicants must be willing to undergo and be able to pass KYC/KYB. 

* Applicants must not be in an OFAC sanctioned jurisdiction or any similar watchlists


## Funding Details

_COTI grant program RFPs are bid-for-service and the Maximum Funding Amount isn’t indicative of the bid amount one should apply for but rather the cap that COTI puts on this particular Request for Proposal. In most cases, winning proposals are significantly less than the Maximum Funding Amount. _

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

1. **Foundry Toolkit Development**
    1. Create a “COTI Foundry Toolkit” written in Solidity, the toolkit must allow installation as a Forge dependency.

    2. Due to lack of native Foundry extensibility, the toolkit can be delivered in the form of embedded Solidity scripts.

    3. Solidity [IR pipeline](https://docs.soliditylang.org/en/latest/ir-breaking-changes.html) should be used where possible to avoid errors, Foundry makes this available via its [optimizer](https://book.getfoundry.sh/reference/forge/forge-build#the-optimizer)

2. **Functionality**  
    1. Installation: users should be able to integrate the toolkit to existing Foundry projects with the existing git-based functionality. For example, assuming the toolkit is hosted in the COTI Github org, installation should be possible with a command such as: \
`forge install coti-io/coti-foundry-toolkit`

    2. Configuration: users should be able to specify necessary configuration to use the toolkit either via their `foundry.toml` configuration or through forge CLI parameters (see [forge script](https://book.getfoundry.sh/reference/forge/forge-script)).

    3. COTI-specific methods and functions should be available to developers in two main ways:
        1. Solidity scripts: users should be able to interact with COTI-specific methods/functions using embedded Solidity scripts. Users should be able to import the relevant script in their contract and use one of its functions inside of it.
        2. CLI: users should be able to interact with the toolkit via the command line by specifying the script they want to execute along with the necessary arguments for such script. \
`forge coti-foundry-toolkit/script/functions/onboard.sol --args "arg1"`

    4. COTI-specific functionality  
        1. Core functions of the [MPC interface](https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/lib/lib_readme.md#functions-1) to be available in the Foundry toolkit (onboarding, offboarding, etc.)
        2. Encrypt data on-chain
        3. Read on-chain encrypted data
        6. Send transactions on-chain with encrypted inputs


### Non-Functional Requirements

1. **Extensibility: **Optimize architecture and development to future iteration of the toolkit.

2. **Performance:** Toolkit and supporting scripts should be architected for optimal performance.

3. **Support**: Provide support for any issues that arise from v1 for up to 12 months


### Technical Requirements

1. **Development Environment**: Utilize/reference COTI v2 SDKs where possible. Provide feedback to the COTI team on the usage of the SDK.

2. **Testing**: Implement comprehensive testing, including unit tests, integration tests, and user acceptance tests.

3. **Code and Documentation**: Provide final solution in a private GitHub repository. Provide clear documentation via README. Optionally, transfer repo to the COTI GitHub organization upon request.


## Support / Follow Through Criteria

_For many projects, there is work that happens in the ecosystem, community, and with your users that continues well beyond general acceptance of the initial delivery. This may include bugs, review of new features contributed by the community, etc. We’ve stipulated below what support and follow through we expect as part of the full lifecycle of your proposal._

* 12mo defect support


## Legal and Compliance

_All applicants must agree to the following additional legal and compliance concerns. _

* All IP created as part of this grant will be developed under the Apache 2.0 license.

* Grantee agrees to transfer all assets created as part of this grant to the COTI Foundation.


## Other Notes


### Useful Links



* [Coti Docs](https://docs.coti.io)
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
* Foundry related resources
    * [Foundry book](https://book.getfoundry.sh/)
        * [Forge script](https://book.getfoundry.sh/reference/forge/forge-script)