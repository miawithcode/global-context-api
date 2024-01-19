# Global Context API

创建全局 Context API，给应用中的所有组件提供数据

1. 在 `context.jsx` 中创建 Context API `AppContext`。
2. 在 `main.jsx` 中用 `<AppContext></AppContext>` 将 `App` 组件 wrap 起来
3. 因为此时组件中嵌套着组件，要用到 Children Prop。在 `AppContext` 中 access to `children` prop
    ```jsx
    const AppContext = ({ children }) => {
      //其他代码
      return (
        <GlobalContext.Provider value={{ name, setName }}>
          {children}
        </GlobalContext.Provider>
      );
    };
    ```
4. 在 `context.jsx` 中设置 Custom Hooks 来使用 `GlobalContext`
    ```jsx
    export const useGlobaleContext = () => useContext(GlobalContext);
    ```