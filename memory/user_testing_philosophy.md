---
name: user_testing_philosophy
description: Layered testing strategy — unit for logic, integration with real DB, E2E for critical paths only
metadata:
  type: user
---

Unit tests: pure logic only — functions with no side effects, reducers, validators. No mocks of internal modules.

Integration tests: data flows with a real database. Mocked DB tests passed while prod migration broke — never mock the DB layer.

E2E: critical user paths only (login, checkout, core flow). Not comprehensive coverage — too slow, too brittle for edge cases.

**How to apply:** When suggesting tests, default to this ladder. Never reach for E2E when an integration test suffices. Never mock internal DB layers.
