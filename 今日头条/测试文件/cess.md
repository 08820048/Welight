## 代码编辑测试


```rust
#[tauri::command]
async fn git_push_set_upstream(dir: String) -> Result<(), String> {
    tauri::async_runtime::spawn_blocking(move || {
        let root = ensure_abs_dir(&dir)?;
        let head = run_git_text(&root, &["branch", "--show-current"])?
            .trim()
            .to_string();
        if head.is_empty() {
            return Err("cannot resolve current branch".to_string());
        }
        let _ = run_git_text(&root, &["push", "-u", "origin", &head])?;
        Ok(())
    })
    .await
    .map_err(|e| e.to_string())?
}
```

## 咋不吃

```ts
ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```试试试试ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
```js
ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```