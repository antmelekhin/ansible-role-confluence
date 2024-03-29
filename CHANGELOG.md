# Changelog

## [1.0.7](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.6...v1.0.7) (2024-03-12)


### Continuous Integration

* update `checkout` action version ([8858838](https://github.com/antmelekhin/ansible-role-confluence/commit/885883840a0944f8c98cb6bbd6c429d2feffb17a))
* update test matrix ([3efc79e](https://github.com/antmelekhin/ansible-role-confluence/commit/3efc79eaaa1d1db98c996d78caa933548c05f373))


### Documentation

* update supported os versions ([42deed0](https://github.com/antmelekhin/ansible-role-confluence/commit/42deed090f680f2436f6f6684fad16b6ba228233))


### Fixes

* **version:** confluence updated to `8.5.7` release ([#12](https://github.com/antmelekhin/ansible-role-confluence/issues/12)) ([ba415b6](https://github.com/antmelekhin/ansible-role-confluence/commit/ba415b6d5add5a0deb80a3de6d3aa2a187d0c13a))


### Styles

* add empty line after ansible comment ([8065874](https://github.com/antmelekhin/ansible-role-confluence/commit/8065874ed04586edb2b342a64d12103527679521))
* rename some task names and minor changes ([#11](https://github.com/antmelekhin/ansible-role-confluence/issues/11)) ([bda7386](https://github.com/antmelekhin/ansible-role-confluence/commit/bda73860076c89fd6ebe7f22b62badbb414695dd))


### Tests

* add tox ([9194b4e](https://github.com/antmelekhin/ansible-role-confluence/commit/9194b4eb2c0a4a0f0c483c0dbcc759ef08e529be))
* fix requirements ([75caced](https://github.com/antmelekhin/ansible-role-confluence/commit/75cacedc1569475173838d739e52fcd62cde25dd))
* use my java ansible role ([60f9d65](https://github.com/antmelekhin/ansible-role-confluence/commit/60f9d6550eac4945bde45280547cd94ea9480bb4))

## [1.0.6](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.5...v1.0.6) (2024-02-13)


### Fixes

* **version:** confluence updated to `8.5.6` release ([#10](https://github.com/antmelekhin/ansible-role-confluence/issues/10)) ([a147ae6](https://github.com/antmelekhin/ansible-role-confluence/commit/a147ae61076ef51a9f6971a329ae75aab12ebb80))

## [1.0.5](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.4...v1.0.5) (2024-01-24)


### Fixes

* **version:** confluence updated to `8.5.5` release ([#9](https://github.com/antmelekhin/ansible-role-confluence/issues/9)) ([5f31c9f](https://github.com/antmelekhin/ansible-role-confluence/commit/5f31c9f437a0cb9e1922a49b63dfff1f2f023a5b))

## [1.0.4](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.3...v1.0.4) (2023-12-12)


### Fixes

* **version:** confluence updated to `8.5.4` release ([#8](https://github.com/antmelekhin/ansible-role-confluence/issues/8)) ([2ea6c0d](https://github.com/antmelekhin/ansible-role-confluence/commit/2ea6c0d892cc21ed96b45765c9093875d7cb39f4))

## [1.0.3](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.2...v1.0.3) (2023-11-08)


### Fixes

* **version:** confluence updated to `8.5.3` release ([#7](https://github.com/antmelekhin/ansible-role-confluence/issues/7)) ([eb11354](https://github.com/antmelekhin/ansible-role-confluence/commit/eb113546032e6dafd79ccc5dba48d0a01aa2f0cc))

## [1.0.2](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.1...v1.0.2) (2023-10-17)


### Continuous Integration

* add release type improv ([882adc7](https://github.com/antmelekhin/ansible-role-confluence/commit/882adc79aba47dea73b3aabb3452840875afb4d2))
* add script and workflow for update version ([#5](https://github.com/antmelekhin/ansible-role-confluence/issues/5)) ([b8cffe7](https://github.com/antmelekhin/ansible-role-confluence/commit/b8cffe7203584b716e3048d6030406374ad3db9e))


### Fixes

* **version:** confluence updated to `8.5.2` release ([#6](https://github.com/antmelekhin/ansible-role-confluence/issues/6)) ([289e303](https://github.com/antmelekhin/ansible-role-confluence/commit/289e30390f82a5e4d383c559e773d681b32b6854))


### Styles

* add quotes in notify name ([353c5a0](https://github.com/antmelekhin/ansible-role-confluence/commit/353c5a088214746edf4140562495271c4b34959b))
* fix jinja2 statement ([8942364](https://github.com/antmelekhin/ansible-role-confluence/commit/8942364c56ae81921c997561a88dbde89e5a03da))


### Tests

* add `tzdata-java` package ([eb78bb0](https://github.com/antmelekhin/ansible-role-confluence/commit/eb78bb0b1f32cd4562219f17eff57cea6b6c2def))

## [1.0.1](https://github.com/antmelekhin/ansible-role-confluence/compare/v1.0.0...v1.0.1) (2023-06-20)


### Continuous Integration

* add `publish` and `release` workflows ([5a3e144](https://github.com/antmelekhin/ansible-role-confluence/commit/5a3e144e44ad6ab255606ff486bb955f063043d7))


### Documentation

* update README and meta ([8be3ef9](https://github.com/antmelekhin/ansible-role-confluence/commit/8be3ef98ee5e09c7241fc2a383bd443974154351))


### Fixes

* mv `daemon_reload` from tasks to handlers ([a2cfdb5](https://github.com/antmelekhin/ansible-role-confluence/commit/a2cfdb588908df1caa687e47c06e382a36f3bcf1))
* reordering key names ([40593c0](https://github.com/antmelekhin/ansible-role-confluence/commit/40593c05c226d8b1e78f8a5706dcdeeac380d5cc))


### Tests

* fix linting rules ([d65ccf7](https://github.com/antmelekhin/ansible-role-confluence/commit/d65ccf7c585c171dc2f56ad5ad5f80ddc2056197))
* use my docker containers in molecule ([9d6233a](https://github.com/antmelekhin/ansible-role-confluence/commit/9d6233ac7ba9a77837ebfc0de69b812588a9c823))
