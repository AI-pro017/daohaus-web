# DAOhaus Web

A web app for finding, joining and creating Moloch DAOs. Moloch DAOs are simple on-chain organizations where members pool funds and vote on proposals together.

This is the original DAOhaus frontend made by [DAOhaus](https://daohaus.club). The DAOhaus team has since moved on to newer apps, so treat this as an archived version that's useful for learning how a DAO frontend talks to Moloch contracts and a subgraph.

## What you can do in the app

- Browse every DAO deployed through the DAOhaus factory, with search and filters.
- Open a DAO's page to see its members, bank, proposals and voting, for both Moloch v1 and v2 DAOs.
- Apply to join a v1 DAO by accepting its member agreement and pledging funds in exchange for shares.
- Summon a new DAO with a step by step form that sets the name, members, deposit token and voting periods.
- See platform wide stats such as total DAOs, members and funds.
- View a member's profile, with their 3Box details where available.

## Tech stack

- React 16 (Create React App)
- Apollo Client and GraphQL, reading from The Graph subgraphs for DAOhaus
- web3.js, Web3Modal and WalletConnect for wallets
- Ant Design, Formik and Chart.js

## Running it locally

The project targets Node.js 12 (see `.nvmrc`), so use nvm or a similar tool to switch versions.

```bash
git clone https://github.com/AI-pro017/daohaus-web.git
cd daohaus-web
yarn install
cp .env.sample .env.local
yarn start
```

Set these in `.env.local`:

| Variable | Description |
| --- | --- |
| `REACT_APP_INFURA_URI` | An Infura (or other) RPC URL for the network |
| `REACT_APP_NETWORK_ID` | Chain ID, for example `1` for mainnet |

The sample file points at Kovan, which has since been shut down along with Rinkeby. Use mainnet or swap in a current testnet with its own factory and subgraph.

## Contract addresses and subgraphs

The mainnet DAOhaus factory is at `0x2840d12d926cc686217bb42B80b662C7D72ee787`, and DAO data comes from the `odyssy-automaton/daohaus` and `daohaus-stats` subgraphs on The Graph's hosted service. The hosted service has been retired, so those endpoints may need replacing with their decentralized network versions.

## Project structure

```text
src/
  views/        Pages: explore, DAO, summon, apply, profile, stats and more
  components/   Shared UI
  contexts/     Wallet and app state
  contracts/    Contract ABIs and helpers
  util/         GraphQL queries and utilities
```

## License

GPL-3.0 or later. See [LICENSE](LICENSE).
