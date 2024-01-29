# 👽 Rust Backend

## Implementing New Handlers with Data Validation

When implementing a new handler in Rust, particularly for data processing or API request handling, it is crucial to ensure that the input data is valid and meets the expected criteria. This is where data validation comes into play.

The `validator` crate in Rust is an excellent tool for this purpose. It offers a comprehensive suite of validators that can be readily used to enforce various constraints on your data structures. From checking string lengths to validating numerical ranges and patterns, `validator` covers a wide array of common validation needs.

### Utilizing the `validator` Crate

Here’s how you can integrate the `validator` crate into your Rust application:

1. **Integration**: Include the `validator` crate in your `Cargo.toml` to get started. This crate provides the `Validate` trait that you can derive for your structs.

2. **Applying Validators**: Use the provided validators to annotate your struct fields. For instance, to ensure a string field is not empty, you can use validators like `length(min = "1")`.

3. **Custom Validators**: For more specific or complex validation logic that isn't covered by the built-in validators, you can define custom validators. For example, `required_not_empty_str` is a custom validator defined in `lib_infra::validator_fn`.

### Example: Validating Handler Input Data

In the context of your Rust application, consider the following struct representing data to be imported into AppFlowy:

```rust
use flowy_derive::ProtoBuf;
use validator::Validate;

#[derive(ProtoBuf, Validate, Default)]
pub struct ImportAppFlowyDataPB {
  #[pb(index = 1)]
  #[validate(custom = "lib_infra::validator_fn::required_not_empty_str")]
  pub path: String,

  #[pb(index = 2, one_of)]
  pub import_container_name: Option<String>,
}
```

In this example:

- The `ImportAppFlowyDataPB` struct is defined with fields that need validation.
- The `path` field is validated using a custom validator `required_not_empty_str` to ensure it's a non-empty string.
- The `import_container_name` field is optional and does not require such strict validation.

### Handling the Validation in Handlers

When writing a handler function, such as `import_appflowy_data_folder_handler`, you should include validation logic to ensure that incoming data meets the expected criteria before proceeding with the handler’s core functionality:

```rust
pub async fn import_appflowy_data_folder_handler(
    data: AFPluginData<ImportAppFlowyDataPB>,
) -> Result<(), FlowyError> {
    // Perform validation
    let data = data.try_into_inner()?;

    // Handler logic goes here
    Ok(())
}
```

In the handler:

- The `try_into_inner` method is called on the `data` object. This method automatically performs all the validations defined in the struct.
- If validation fails, an error is returned. This error can be converted or logged according to your application's error handling strategy.

