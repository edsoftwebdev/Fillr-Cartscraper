# Fillr Desktop Autofill Library

## Installation

```bash
$> npm install @fillr_letspop/desktop-autofill
```

## Usage

- Configure dev key and secret key
- Implement profile listener
- Declare user profile data

```typescript
import FillrController from "@fillr_letspop/desktop-autofill";
// https://github.com/Fillr/browser-example-integration/blob/master/profile-data-en-us.ts
// import ProfileData from './profile-data-en-us';

const profileData = {
  "PersonalDetails.FirstName": "John",
  "PersonalDetails.Honorific": "Mr.",
  "PersonalDetails.LastName": "Wick",
  }

const devKey = '';
const secretKey = '';
const profileDataHandler = new ProfileDataInterface((mappings) => {
  mappings.profile = ProfileData; 
  fillr.performFill(mappings);
})

const fillr = new FillrController(devKey, secretKey, profileDataHandler);
```

## Reference
https://github.com/Fillr/browser-example-integration

## License

[Copyright (c) 2015-present Pop Tech Pty Ltd.](LICENSE)

