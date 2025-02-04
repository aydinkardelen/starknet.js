---
id: 'ec.weierstrass'
title: 'Namespace: weierstrass'
sidebar_label: 'weierstrass'
custom_edit_url: null
---

[ec](ec.md).weierstrass

## Interfaces

- [ProjPointType](../interfaces/ec.weierstrass.ProjPointType.md)
- [ProjConstructor](../interfaces/ec.weierstrass.ProjConstructor.md)
- [SignatureType](../interfaces/ec.weierstrass.SignatureType.md)

## Type Aliases

### AffinePoint

Ƭ **AffinePoint**<`T`\>: { `x`: `T` ; `y`: `T` } & { `z?`: `never` ; `t?`: `never` }

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Defined in

node_modules/@noble/curves/abstract/curve.d.ts:3

---

### BasicWCurve

Ƭ **BasicWCurve**<`T`\>: `BasicCurve`<`T`\> & { `a`: `T` ; `b`: `T` ; `allowedPrivateKeyLengths?`: readonly `number`[] ; `wrapPrivateKey?`: `boolean` ; `endo?`: `EndomorphismOpts` ; `isTorsionFree?`: (`c`: [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`T`\>, `point`: [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`T`\>) => `boolean` ; `clearCofactor?`: (`c`: [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`T`\>, `point`: [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`T`\>) => [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`T`\> }

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:17

---

### SignOpts

Ƭ **SignOpts**: `Object`

#### Type declaration

| Name            | Type      |
| :-------------- | :-------- |
| `lowS?`         | `boolean` |
| `extraEntropy?` | `Entropy` |
| `prehash?`      | `boolean` |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:27

---

### VerOpts

Ƭ **VerOpts**: `Object`

#### Type declaration

| Name       | Type      |
| :--------- | :-------- |
| `lowS?`    | `boolean` |
| `prehash?` | `boolean` |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:32

---

### CurvePointsType

Ƭ **CurvePointsType**<`T`\>: [`BasicWCurve`](ec.weierstrass.md#basicwcurve)<`T`\> & { `fromBytes`: (`bytes`: `Uint8Array`) => [`AffinePoint`](ec.weierstrass.md#affinepoint)<`T`\> ; `toBytes`: (`c`: [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`T`\>, `point`: [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`T`\>, `compressed`: `boolean`) => `Uint8Array` }

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:80

---

### CurvePointsRes

Ƭ **CurvePointsRes**<`T`\>: `Object`

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Type declaration

| Name                     | Type                                                                       |
| :----------------------- | :------------------------------------------------------------------------- |
| `ProjectivePoint`        | [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`T`\> |
| `normPrivateKeyToScalar` | (`key`: `PrivKey`) => `bigint`                                             |
| `weierstrassEquation`    | (`x`: `T`) => `T`                                                          |
| `isWithinCurveOrder`     | (`num`: `bigint`) => `boolean`                                             |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:84

---

### SignatureConstructor

Ƭ **SignatureConstructor**: `Object`

#### Call signature

• **new SignatureConstructor**(`r`, `s`): [`SignatureType`](../interfaces/ec.weierstrass.SignatureType.md)

##### Parameters

| Name | Type     |
| :--- | :------- |
| `r`  | `bigint` |
| `s`  | `bigint` |

##### Returns

[`SignatureType`](../interfaces/ec.weierstrass.SignatureType.md)

#### Type declaration

| Name          | Type                                                                               |
| :------------ | :--------------------------------------------------------------------------------- |
| `fromCompact` | (`hex`: `Hex`) => [`SignatureType`](../interfaces/ec.weierstrass.SignatureType.md) |
| `fromDER`     | (`hex`: `Hex`) => [`SignatureType`](../interfaces/ec.weierstrass.SignatureType.md) |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:110

---

### PubKey

Ƭ **PubKey**: `Hex` \| [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`bigint`\>

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:119

---

### CurveType

Ƭ **CurveType**: [`BasicWCurve`](ec.weierstrass.md#basicwcurve)<`bigint`\> & { `hash`: `CHash` ; `hmac`: `HmacFnSync` ; `randomBytes`: (`bytesLength?`: `number`) => `Uint8Array` ; `lowS?`: `boolean` ; `bits2int?`: (`bytes`: `Uint8Array`) => `bigint` ; `bits2int_modN?`: (`bytes`: `Uint8Array`) => `bigint` }

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:120

---

### CurveFn

Ƭ **CurveFn**: `Object`

#### Type declaration

| Name                           | Type                                                                                                                                                                                                                                                                                                                                                                                |
| :----------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `CURVE`                        | `ReturnType`<typeof `validateOpts`\>                                                                                                                                                                                                                                                                                                                                                |
| `getPublicKey`                 | (`privateKey`: `PrivKey`, `isCompressed?`: `boolean`) => `Uint8Array`                                                                                                                                                                                                                                                                                                               |
| `getSharedSecret`              | (`privateA`: `PrivKey`, `publicB`: `Hex`, `isCompressed?`: `boolean`) => `Uint8Array`                                                                                                                                                                                                                                                                                               |
| `sign`                         | (`msgHash`: `Hex`, `privKey`: `PrivKey`, `opts?`: [`SignOpts`](ec.weierstrass.md#signopts)) => [`SignatureType`](../interfaces/ec.weierstrass.SignatureType.md)                                                                                                                                                                                                                     |
| `verify`                       | (`signature`: `Hex` \| `SignatureLike`, `msgHash`: `Hex`, `publicKey`: `Hex`, `opts?`: [`VerOpts`](ec.weierstrass.md#veropts)) => `boolean`                                                                                                                                                                                                                                         |
| `ProjectivePoint`              | [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`bigint`\>                                                                                                                                                                                                                                                                                                     |
| `Signature`                    | [`SignatureConstructor`](ec.weierstrass.md#signatureconstructor)                                                                                                                                                                                                                                                                                                                    |
| `utils`                        | { `normPrivateKeyToScalar`: (`key`: `PrivKey`) => `bigint` ; `randomPrivateKey`: () => `Uint8Array` ; `precompute`: (`windowSize?`: `number`, `point?`: [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`bigint`\>) => [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`bigint`\> ; `isValidPrivateKey`: (`privateKey`: `PrivKey`) => `boolean` } |
| `utils.normPrivateKeyToScalar` | (`key`: `PrivKey`) => `bigint`                                                                                                                                                                                                                                                                                                                                                      |
| `utils.randomPrivateKey`       | () => `Uint8Array`                                                                                                                                                                                                                                                                                                                                                                  |
| `utils.precompute`             | (`windowSize?`: `number`, `point?`: [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`bigint`\>) => [`ProjPointType`](../interfaces/ec.weierstrass.ProjPointType.md)<`bigint`\>                                                                                                                                                                                     |
| `utils.isValidPrivateKey`      | [object Object]                                                                                                                                                                                                                                                                                                                                                                     |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:152

## Functions

### weierstrassPoints

▸ **weierstrassPoints**<`T`\>(`opts`): `Object`

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Parameters

| Name   | Type                                                         |
| :----- | :----------------------------------------------------------- |
| `opts` | [`CurvePointsType`](ec.weierstrass.md#curvepointstype)<`T`\> |

#### Returns

`Object`

| Name                     | Type                                                                       |
| :----------------------- | :------------------------------------------------------------------------- |
| `ProjectivePoint`        | [`ProjConstructor`](../interfaces/ec.weierstrass.ProjConstructor.md)<`T`\> |
| `normPrivateKeyToScalar` | (`key`: `PrivKey`) => `bigint`                                             |
| `weierstrassEquation`    | (`x`: `T`) => `T`                                                          |
| `isWithinCurveOrder`     | (`num`: `bigint`) => `boolean`                                             |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:90

---

### weierstrass

▸ **weierstrass**(`curveDef`): [`CurveFn`](ec.weierstrass.md#curvefn)

#### Parameters

| Name       | Type                                       |
| :--------- | :----------------------------------------- |
| `curveDef` | [`CurveType`](ec.weierstrass.md#curvetype) |

#### Returns

[`CurveFn`](ec.weierstrass.md#curvefn)

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:167

---

### SWUFpSqrtRatio

▸ **SWUFpSqrtRatio**<`T`\>(`Fp`, `Z`): (`u`: `T`, `v`: `T`) => { `isValid`: `boolean` ; `value`: `T` }

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Parameters

| Name | Type          |
| :--- | :------------ |
| `Fp` | `Field`<`T`\> |
| `Z`  | `T`           |

#### Returns

`fn`

▸ (`u`, `v`): `Object`

##### Parameters

| Name | Type |
| :--- | :--- |
| `u`  | `T`  |
| `v`  | `T`  |

##### Returns

`Object`

| Name      | Type      |
| :-------- | :-------- |
| `isValid` | `boolean` |
| `value`   | `T`       |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:168

---

### mapToCurveSimpleSWU

▸ **mapToCurveSimpleSWU**<`T`\>(`Fp`, `opts`): (`u`: `T`) => { `x`: `T` ; `y`: `T` }

#### Type parameters

| Name |
| :--- |
| `T`  |

#### Parameters

| Name     | Type          |
| :------- | :------------ |
| `Fp`     | `Field`<`T`\> |
| `opts`   | `Object`      |
| `opts.A` | `T`           |
| `opts.B` | `T`           |
| `opts.Z` | `T`           |

#### Returns

`fn`

▸ (`u`): `Object`

##### Parameters

| Name | Type |
| :--- | :--- |
| `u`  | `T`  |

##### Returns

`Object`

| Name | Type |
| :--- | :--- |
| `x`  | `T`  |
| `y`  | `T`  |

#### Defined in

node_modules/@noble/curves/abstract/weierstrass.d.ts:172
