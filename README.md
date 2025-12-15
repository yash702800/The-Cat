# The Cat - Non-monetary UTXO Cleanup

This repository contains the working draft of a Bitcoin Improvement Proposal (BIP) tentatively titled “Non-monetary UTXO Cleanup (The Cat)”.

It documents a soft-fork consensus change and new spending rules intended to remove an existing, snapshot-based set of non-monetary UTXOs (NMUs) created by protocols such as Ordinals and Stamps, by making those UTXOs permanently unspendable and eligible for removal from the UTXO set.

The BIP itself does **not** define any new relay or standardness policies for future transactions. Rather than restricting new transactions directly, The Cat aims to remove demand for such activity by eliminating the financial incentives for creating NMUs in the first place.

For motivation, tradeoffs, and the discussion of censorship resistance, see the [Rationale](./bip-the-cat.md#rationale) section of the draft, in particular [Censorship resistance and scope](./bip-the-cat.md#censorship-resistance-and-scope).

## Files

- [`bip-the-cat.md`](./bip-the-cat.md) - main BIP draft (specification, rationale, references)
- Additional notes, scripts, and data may be added over time.

This repository serves as the public discussion link referenced in the BIP header
and in any future pull request to the `bitcoin/bips` repository.

---

## Quick links: rationale and FAQ

- [Rationale](./bip-the-cat.md#rationale)
- [Censorship resistance and scope](./bip-the-cat.md#censorship-resistance-and-scope)
- [External indexers, determinism, and reproducibility](./bip-the-cat.md#external-indexers-determinism-and-reproducibility)
- [Centralization and trust model for NMU generation](./bip-the-cat.md#centralization-and-trust-model-for-nmu-generation)
- [Backward compatibility](./bip-the-cat.md#backward-compatibility)

The FAQ in the draft also answers common questions directly:

- Do I need to run Ord or Stamps on my node?  
  See [Do node operators need to run Ord or Stamps?](./bip-the-cat.md#do-node-operators-need-to-run-ord-or-stamps)

- What exactly do the reference indexers consider an NMU?  
  See [What rules do the reference indexers actually use to decide which UTXOs are NMUs?](./bip-the-cat.md#what-rules-do-the-reference-indexers-actually-use-to-decide-which-utxos-are-nmus)

- Will spammers just find workarounds and keep spamming anyway?  
  See [Won't spammers just make workarounds and spam anyway?](./bip-the-cat.md#wont-spammers-just-make-workarounds-and-spam-anyway)

- Can users "escape" The Cat by spending dust after the snapshot?  
  See [Can’t users just spend their NMUs after the snapshot, removing them from the list?](./bip-the-cat.md#cant-users-just-spend-their-nmus-after-the-snapshot-removing-them-from-the-list)

- Will my "inscribed sats" in normal wallet UTXOs get Catted?  
  See [What if some of my UTXOs contain “inscribed sats”? Won’t those get “Catted”?](./bip-the-cat.md#what-if-some-of-my-utxos-contain-inscribed-sats-wont-those-get-catted)

---

## Supporting stats and charts

See [`charts/`](./charts) for supporting statistics and visualizations that
illustrate the scale and structure of inscription-related UTXOs.

---

### Process note: mailing list moderation

The usual first step for a BIP is to circulate a detailed proposal on the Bitcoin Development Mailing List and gather on-list technical feedback before requesting a BIP number.

In December 2025, multiple attempts were made to post The Cat to the mailing list. These initial messages were held in moderation and did not appear on the public archive, despite being a fully worked technical draft.

The proposal was later allowed through and discussion is now taking place on the list. After it was posted, Greg Maxwell responded. I replied on **December 11, 2025**, but as of this writing that reply has still not appeared on the public archive, while additional replies in the same thread (including multiple follow-ups by Greg to other participants responding to points I raised) have been approved and posted. The practical effect is that the on-list discussion has, at times, felt materially one-sided.

Regardless of venue, this repository is the canonical home for the draft specification and edits to The Cat. Feedback is welcome here via issues and pull requests, and I’m also participating in discussion on the Bitcoin-dev mailing list and on Delving Bitcoin.

