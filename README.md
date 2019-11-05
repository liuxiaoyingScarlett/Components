# Components
## 移动端toast

+ 控制样式、组件内部控制展示时间
+ `toast(:msg="toastMsg",:time="times",ref="toast")`

## 移动端modal

+ 样式、遮罩层

+ `    modal(:title="modalTitle",:confirmText="confirmText",:cancelText="cancelText",:showModal="isModal",@cancel="isModal = false",@confirm="confirmModal")`
