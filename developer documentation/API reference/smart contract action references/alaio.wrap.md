# Wrap

**Type:** class

The `alaio.wrap` system contract grants block producers the ability to pass authorization checks or bypass privileged actions with 15/21 prodcuer approval and consequently clarifies block producers superuser actions. It also makes these actions easier to audit.

Block producters are not given any additional powers or privileges that do not already exist with the ALAIO based blockchains. While it is being implemented, in an ALAIO based blockchain, 15/21 block producers can alter an account's permissions or change an account's contract code if they deemed it is advantageous for the blockchain and community. On the other hand, the residing method is opaque and leaves unwanted side effects of certain system accounts, and thus the `alaio.wrap` contract resolves this issue by providing a simpler method of following through with important governance actions. 

Only one actions is implemented by the `alaio.wrap` system contract and that is the `exec` actions. the actions permits for execution of a transaction, which is passed to the exec method in the configuration of a packed transaction in json form through the 'trx' parameter and the `executer` account that executes the arrangement. The same `executer` account will also be used to pay the RAM and CPU fees needed to execute the transaction.

## exec

**Type:** void

Execute action.

Execute a transaction while bypassing regular authorization checks.

Preconditions:

* Requires authorization of alaio.wrap which needs to be a privileged account.

Postconditions:

* Deferred transaction RAM usage is billed to 'executer'

Parameter Name | Description
--- | ---
executer | - account executing the transaction,
trx | - the transaction to be executed.
