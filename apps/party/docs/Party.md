# Party Context

The `Party` entity is the foundational object for all actors in the system. 

## Lifecycle
New `Party` records default to a status of `PARTY_ENABLED`. Any change in status is recorded in the `PartyStatus` history table to maintain a full audit trail of the party's lifecycle.

## Relationships
- **Person**: A sub-type representing individuals (`partyTypeId="PERSON"`).
- **PartyGroup**: A sub-type representing organizations (`partyTypeId="PARTY_GROUP"`).

## Business Logic
1. **ID Constraints**: When manually specifying a `partyId`, it should not be purely numeric (e.g., `12345` is invalid) to avoid collisions with auto-generated sequential IDs.
2. **Type Integrity**: A party's type (`PERSON` or `PARTY_GROUP`) is immutable once created. You cannot convert a Person to a PartyGroup.
3. **Traceability**: All parties track their creation and last modification dates, along with the user ID of the person who performed the action.

## Fields
- **party_id**: Unique identifier.
- **party_type_id**: Distinguishes between PERSON and PARTY_GROUP.
