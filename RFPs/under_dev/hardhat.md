# COTI - Hardhat Plugin


## Background

COTI is a privacy preserving L2 on ethereum. It allows secure multi party computation using garbled circuits. Parties can jointly compute one or more functions over their inputs and keep the inputs private. Users can do MPC with encrypted data, never having to reveal sensitive information.

COTI introduces unique precompiles and methods that extend the EVM into the gcEVM (garbled-circuits EVM). As such, supporting these methods in an easy, familiar way is important for developers.


## Objectives



* Create a Hardhat plugin written in Typescript, delivered as an npm package
* Include the most important functionality for COTI developers using Hardhat plugin primitives
* Design and implement in an extensible manner to allow for future development. Architecture and documentation should allow multiple parties to contribute to the future development/additions for the COTI plugin.


## Functional Requirements



1. **Hardhat Plugin Development**
    1. Create a “COTI Hardhat Plugin” written in Typescript, following Nomic’s best practices (see [Building Plugins](https://hardhat.org/hardhat-runner/docs/advanced/building-plugins))

    2. Plugin to be delivered as an npm package to end users. Public package to be published by COTI team only, initial package can be delivered as a private package for testing purposes.

2. **Functionality**
    1. COTI-specific methods and functions should be available to developers in two main ways:
        1. CLI: appending the service and method name to CLI commands, for example: \
`npx hardhat coti:{service} [method] [--args] \
`(naming conventions for illustrative purposes only)
        2. Hardhat Tasks: integrating COTI services as a subtask in the user’s own Hardhat tasks, for example: \
`hre.run("coti:{service}:{method}", { ...args });`
        3. Methods in Hardhat environment: users must be able to access COTI services in the Hardhat environment, for example: \
`hre.coti.{service}.{method}(...args);`

    2. COTI-specific functionality
        1. Core functions of the [MPC interface](https://github.com/coti-io/confidentiality-contracts/blob/main/contracts/lib/lib_readme.md#functions-1) to be available in Hardhat (onboarding, offboarding, etc.)
        2. Encrypt data on-chain
        3. Read on-chain encrypted data
        4. Send transactions on-chain with encrypted inputs


## Non-Functional Requirements



1. **Extensibility**: Optimize architecture and development to future iteration of the plugin.

2. **Performance:** Keep startup time short to provide optimal user experience. Hardhat and its plugins delay any slow import or initialization until the very last moment. To do so, you can use `lazyObject`, and `lazyFunction` from `hardhat/plugins`. An example on how to use them is present in [src/index.ts](https://github.com/NomicFoundation/hardhat-ts-plugin-boilerplate/blob/master/src/index.ts) of Hardhat’s boilerplate repo.

3. **Support**: Provide support for any issues that arise from v1 for up to 12 months


## Technical Requirements



1. **Development Environment**: Utilize/reference COTI v2 SDKs where possible. Provide feedback to the COTI team on the usage of the SDK.

2. **Testing**: Implement comprehensive testing, including unit tests, integration tests, and user acceptance tests.

3. **Code and Documentation**: Provide final solution in a private GitHub repository. Provide clear documentation via README. Optionally, transfer repo to the COTI GitHub organization upon request.


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
* Hardhat related resources
    * [Building plugins - Hardhat Docs](https://hardhat.org/hardhat-runner/docs/advanced/building-plugins)
    * [Hardhat TypeScript plugin boilerplate](https://github.com/NomicFoundation/hardhat-ts-plugin-boilerplate/)
    * [Extending the Hardhat Runtime Environment - Docs](https://hardhat.org/hardhat-runner/docs/advanced/hardhat-runtime-environment#extending-the-hre)
    * Plugin sample:[ hardhat-fund-link](https://github.com/appliedblockchain/chainlink-consumer/tree/master/plugins/fund-link) 
    * Plugin sample: [hardhat-log-remover](https://github.com/ItsNickBarry/hardhat-log-remover)