# Relative paths to JSON Schema issue in Zed

Zed currently has (seemingly) two separate bugs in both JSON and YAML language servers that prevents users from configuring via settings JSON schemas using relative paths. You can open this project in both VSCode and Zed and all "works" as intended in VSCode, while Zed does not.

**To ensure its easy to indicate that things are working as expected all example files are intentionally "wrong" with the provided schema (number <> string)!**

## YAML
Somehow Zed does something to the YAML language server settings that causes slashes in relative paths to be converted to comma's.
This prevents anyone from providing JSON schemas within a repository. If you keep the JSON schemas at the root it works as expected.

## JSON
Weirdly enough relative JSON schema also do not work in Zed. However, here it seems the paths are always relative to the root / and NOT relative to the project working directory.

## References
- https://github.com/zed-industries/zed/discussions/14528
