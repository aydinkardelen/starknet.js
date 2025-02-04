---
id: 'ec.starkCurve'
title: 'Namespace: starkCurve'
sidebar_label: 'starkCurve'
custom_edit_url: null
---

[ec](ec.md).starkCurve

## Type Aliases

### ProjectivePoint

Ƭ **ProjectivePoint**: `ProjPointType`<`bigint`\>

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:6

node_modules/micro-starknet/lib/index.d.ts:44

---

### PoseidonOpts

Ƭ **PoseidonOpts**: `Object`

#### Type declaration

| Name            | Type                |
| :-------------- | :------------------ |
| `Fp`            | `IField`<`bigint`\> |
| `rate`          | `number`            |
| `capacity`      | `number`            |
| `roundsFull`    | `number`            |
| `roundsPartial` | `number`            |

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:63

---

### PoseidonFn

Ƭ **PoseidonFn**: `ReturnType`<typeof `poseidon`\> & { `m`: `number` ; `rate`: `number` ; `capacity`: `number` }

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:70

## Variables

### \_starkCurve

• `Const` **\_starkCurve**: `CurveFn`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:7

---

### CURVE

• `Const` **CURVE**: `Readonly`<{ `nBitLength`: `number` ; `nByteLength`: `number` ; `Fp`: `IField`<`bigint`\> ; `n`: `bigint` ; `h`: `bigint` ; `hEff?`: `bigint` ; `Gx`: `bigint` ; `Gy`: `bigint` ; `allowInfinityPoint?`: `boolean` ; `a`: `bigint` ; `b`: `bigint` ; `allowedPrivateKeyLengths?`: readonly `number`[] ; `wrapPrivateKey?`: `boolean` ; `endo?`: { `beta`: `bigint` ; `splitScalar`: (`k`: `bigint`) => { `k1neg`: `boolean` ; `k1`: `bigint` ; `k2neg`: `boolean` ; `k2`: `bigint` } } ; `isTorsionFree?`: (`c`: `ProjConstructor`, `point`: `ProjPointType`<`bigint`\>) => `boolean` ; `clearCofactor?`: (`c`: `ProjConstructor`, `point`: `ProjPointType`<`bigint`\>) => `ProjPointType`<`bigint`\> ; `hash`: `u.CHash` ; `hmac`: (`key`: `Uint8Array`, ...`messages`: `Uint8Array`[]) => `Uint8Array` ; `randomBytes`: (`bytesLength?`: `number`) => `Uint8Array` ; `lowS`: `boolean` ; `bits2int?`: (`bytes`: `Uint8Array`) => `bigint` ; `bits2int_modN?`: (`bytes`: `Uint8Array`) => `bigint` ; `p`: `bigint` }\>

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:12

---

### ProjectivePoint

• **ProjectivePoint**: `ProjConstructor`<`bigint`\>

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:6

node_modules/micro-starknet/lib/index.d.ts:44

---

### Signature

• `Const` **Signature**: `SignatureConstructor`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:44

---

### utils

• `Const` **utils**: `Object`

#### Type declaration

| Name                     | Type                                                                                          |
| :----------------------- | :-------------------------------------------------------------------------------------------- |
| `normPrivateKeyToScalar` | (`key`: `u.PrivKey`) => `bigint`                                                              |
| `randomPrivateKey`       | () => `Uint8Array`                                                                            |
| `precompute`             | (`windowSize?`: `number`, `point?`: `ProjPointType`<`bigint`\>) => `ProjPointType`<`bigint`\> |
| `isValidPrivateKey`      | (`privateKey`: `PrivKey`) => `boolean`                                                        |

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:44

---

### Fp253

• `Const` **Fp253**: `Readonly`<`IField`<`bigint`\> & `Required`<`Pick`<`IField`<`bigint`\>, `"isOdd"`\>\>\>

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:60

---

### Fp251

• `Const` **Fp251**: `Readonly`<`IField`<`bigint`\> & `Required`<`Pick`<`IField`<`bigint`\>, `"isOdd"`\>\>\>

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:61

## Functions

### getPublicKey

▸ **getPublicKey**(`privKey`, `isCompressed?`): `Uint8Array`

#### Parameters

| Name            | Type      |
| :-------------- | :-------- |
| `privKey`       | `Hex`     |
| `isCompressed?` | `boolean` |

#### Returns

`Uint8Array`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:8

---

### getSharedSecret

▸ **getSharedSecret**(`privKeyA`, `pubKeyB`): `Uint8Array`

#### Parameters

| Name       | Type  |
| :--------- | :---- |
| `privKeyA` | `Hex` |
| `pubKeyB`  | `Hex` |

#### Returns

`Uint8Array`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:9

---

### sign

▸ **sign**(`msgHash`, `privKey`, `opts?`): `SignatureType`

#### Parameters

| Name      | Type  |
| :-------- | :---- |
| `msgHash` | `Hex` |
| `privKey` | `Hex` |
| `opts?`   | `any` |

#### Returns

`SignatureType`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:10

---

### verify

▸ **verify**(`signature`, `msgHash`, `pubKey`): `boolean`

#### Parameters

| Name        | Type                     |
| :---------- | :----------------------- |
| `signature` | `Hex` \| `SignatureType` |
| `msgHash`   | `Hex`                    |
| `pubKey`    | `Hex`                    |

#### Returns

`boolean`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:11

---

### grindKey

▸ **grindKey**(`seed`): `string`

#### Parameters

| Name   | Type  |
| :----- | :---- |
| `seed` | `Hex` |

#### Returns

`string`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:51

---

### getStarkKey

▸ **getStarkKey**(`privateKey`): `string`

#### Parameters

| Name         | Type  |
| :----------- | :---- |
| `privateKey` | `Hex` |

#### Returns

`string`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:52

---

### ethSigToPrivate

▸ **ethSigToPrivate**(`signature`): `string`

#### Parameters

| Name        | Type     |
| :---------- | :------- |
| `signature` | `string` |

#### Returns

`string`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:53

---

### getAccountPath

▸ **getAccountPath**(`layer`, `application`, `ethereumAddress`, `index`): `string`

#### Parameters

| Name              | Type     |
| :---------------- | :------- |
| `layer`           | `string` |
| `application`     | `string` |
| `ethereumAddress` | `string` |
| `index`           | `number` |

#### Returns

`string`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:54

---

### pedersen

▸ **pedersen**(`x`, `y`): `string`

#### Parameters

| Name | Type          |
| :--- | :------------ |
| `x`  | `PedersenArg` |
| `y`  | `PedersenArg` |

#### Returns

`string`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:56

---

### hashChain

▸ **hashChain**(`data`, `fn?`): `PedersenArg`

#### Parameters

| Name   | Type                                                 |
| :----- | :--------------------------------------------------- |
| `data` | `PedersenArg`[]                                      |
| `fn?`  | (`x`: `PedersenArg`, `y`: `PedersenArg`) => `string` |

#### Returns

`PedersenArg`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:57

---

### \_poseidonMDS

▸ **\_poseidonMDS**(`Fp`, `name`, `m`, `attempt?`): `bigint`[][]

#### Parameters

| Name       | Type                |
| :--------- | :------------------ |
| `Fp`       | `IField`<`bigint`\> |
| `name`     | `string`            |
| `m`        | `number`            |
| `attempt?` | `number`            |

#### Returns

`bigint`[][]

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:62

---

### poseidonBasic

▸ **poseidonBasic**(`opts`, `mds`): [`PoseidonFn`](ec.starkCurve.md#poseidonfn)

#### Parameters

| Name   | Type                                            |
| :----- | :---------------------------------------------- |
| `opts` | [`PoseidonOpts`](ec.starkCurve.md#poseidonopts) |
| `mds`  | `bigint`[][]                                    |

#### Returns

[`PoseidonFn`](ec.starkCurve.md#poseidonfn)

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:75

---

### poseidonCreate

▸ **poseidonCreate**(`opts`, `mdsAttempt?`): [`PoseidonFn`](ec.starkCurve.md#poseidonfn)

#### Parameters

| Name          | Type                                            |
| :------------ | :---------------------------------------------- |
| `opts`        | [`PoseidonOpts`](ec.starkCurve.md#poseidonopts) |
| `mdsAttempt?` | `number`                                        |

#### Returns

[`PoseidonFn`](ec.starkCurve.md#poseidonfn)

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:76

---

### poseidonHash

▸ **poseidonHash**(`x`, `y`, `fn?`): `bigint`

#### Parameters

| Name  | Type                                        |
| :---- | :------------------------------------------ |
| `x`   | `bigint`                                    |
| `y`   | `bigint`                                    |
| `fn?` | [`PoseidonFn`](ec.starkCurve.md#poseidonfn) |

#### Returns

`bigint`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:78

---

### poseidonHashFunc

▸ **poseidonHashFunc**(`x`, `y`, `fn?`): `Uint8Array`

#### Parameters

| Name  | Type                                        |
| :---- | :------------------------------------------ |
| `x`   | `Uint8Array`                                |
| `y`   | `Uint8Array`                                |
| `fn?` | [`PoseidonFn`](ec.starkCurve.md#poseidonfn) |

#### Returns

`Uint8Array`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:79

---

### poseidonHashSingle

▸ **poseidonHashSingle**(`x`, `fn?`): `bigint`

#### Parameters

| Name  | Type                                        |
| :---- | :------------------------------------------ |
| `x`   | `bigint`                                    |
| `fn?` | [`PoseidonFn`](ec.starkCurve.md#poseidonfn) |

#### Returns

`bigint`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:80

---

### poseidonHashMany

▸ **poseidonHashMany**(`values`, `fn?`): `bigint`

#### Parameters

| Name     | Type                                        |
| :------- | :------------------------------------------ |
| `values` | `bigint`[]                                  |
| `fn?`    | [`PoseidonFn`](ec.starkCurve.md#poseidonfn) |

#### Returns

`bigint`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:81

---

### computeHashOnElements

▸ **computeHashOnElements**(`data`, `fn?`): `PedersenArg`

#### Parameters

| Name   | Type                                                 |
| :----- | :--------------------------------------------------- |
| `data` | `PedersenArg`[]                                      |
| `fn?`  | (`x`: `PedersenArg`, `y`: `PedersenArg`) => `string` |

#### Returns

`PedersenArg`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:58

---

### keccak

▸ **keccak**(`data`): `bigint`

#### Parameters

| Name   | Type         |
| :----- | :----------- |
| `data` | `Uint8Array` |

#### Returns

`bigint`

#### Defined in

node_modules/micro-starknet/lib/index.d.ts:59

---

### poseidonSmall

▸ **poseidonSmall**(`values`): `bigint`[]

#### Parameters

| Name     | Type       |
| :------- | :--------- |
| `values` | `bigint`[] |

#### Returns

`bigint`[]

#### Defined in

node_modules/micro-starknet/node_modules/@noble/curves/abstract/poseidon.d.ts:27
