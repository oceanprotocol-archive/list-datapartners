[![banner](https://raw.githubusercontent.com/oceanprotocol/art/master/github/repo-banner%402x.png)](https://oceanprotocol.com)

<h1 align="center" title="list-datapartners">
   <img width="300" src="https://user-images.githubusercontent.com/90316/98151631-c14cd180-1ed0-11eb-91f8-f8fd73f92b29.png" /><br />
</h1>

> Ocean Protocol's Data Partners list

---

**This list has been deprecated with the release of decentralized profiles:**
**https://twitter.com/shipping_ocean/status/1332280305605103616**

---

- [🤿 List Schema](#-list-schema)
- [🏄‍♀️ List Usage](#️-list-usage)
- [⬆️ Releases](#️-releases)
- [🏛 License](#-license)

---

## 🤿 List Schema

For each partner:

```json
{
  "name": "Partner Company Name",
  "accounts": ["0x00000000000000000000"],
  "links": {
    "Home": "https://website.com",
    "Twitter": "https://twitter.com/@HANDLE"
  }
},
{
   ...
}
```

## 🏄‍♀️ List Usage

```bash
npm i @oceanprotocol/list-datapartners
```

This list is published as a npm module and the [`market`](https://github.com/oceanprotocol/market) uses it as a dependency to enhance the UI for those data partners.

After every change, a new version of the list needs to be released.

You can also directly fetch the list from the `main` branch:

```text
https://raw.githubusercontent.com/oceanprotocol/list-datapartners/main/list-datapartners.json
```

JavaScript usage:

```js
import listPartners from '@oceanprotocol/list-datapartners'

// old-school
const listPartners = require('@oceanprotocol/list-datapartners')
```

TypeScript usage:

```ts
import listPartners from '@oceanprotocol/list-datapartners'
import { PartnerData } from '@oceanprotocol/list-datapartners/types'
```

## ⬆️ Releases

Releases are managed semi-automatically. They are always manually triggered from a developer's machine with release scripts.

From a clean `main` branch you can run the release task bumping the version accordingly based on semantic versioning:

```bash
npm run release
```

The task does the following:

- bumps the project version in `package.json`, `package-lock.json`
- auto-generates and updates the CHANGELOG.md file from commit messages
- creates a Git tag
- commits and pushes everything
- creates a GitHub release with commit messages as description
- Git tag push will trigger Travis to do a npm release

For the GitHub releases steps a GitHub personal access token, exported as `GITHUB_TOKEN` is required. [Setup](https://github.com/release-it/release-it#github-releases)

## 🏛 License

```text
Copyright 2020 Ocean Protocol Foundation Ltd.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
