# Implementation of a multiparty wallet-like consensus contract

## Features
* One admin address who can add remove addresses from the owners of the wallet contract
* Ability of the of any owner to submit proposal
* Ability of the remaining wallet owners to approve the proposal
* Ability of the owner of the proposal to call an executeProposal function once the set threshold has been reached
* Ability of the the admin to change the percentage approval for the proposal

## Available functions and Implementation Conditions
*  setThreshold: Conditions >>> onlyAdmin, thresholdNotMoreThan100
* addWalletOwner: Conditions >>> onlyAdmin, notAddressZero, walletHadNotBeenAdded
*  addWalletOwners: Conditions >>> onlyAdmin, walletsLengthLessThan30, notAddressZero, walletHadNotBeenAdded
* removeWalletOwner: Conditions >>> onlyAdmin, notAddressZero, walletHadBeenAdded
*   removeWalletOwners: Conditions >>> onlyAdmin, walletsLengthLessThan30, notAddressZero, walletHadBeenAdded
* submitProposal: Conditions >>> isWalletOwner, proposalDoesNotAlreadyExist
* approveProposal: Conditions >>> isWalletOwner, hasNotApprovedProposal
* executeProposal: Conditions >>> isWalletOwner, isProposalOwner, hasReachedThreshold
