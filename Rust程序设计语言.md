# Rust程序设计语言

## 参考资料

- https://www.rust-lang.org
- https://www.rust-lang.org/zh-CN/
- https://doc.rust-lang.org/stable/book/
- https://www.yuque.com/qyuhen/rust

# 核心特性

> 核心思想、核心原理、核心特性、适用场景、核心概念

# Glossary

## List

- 宏-macro: 模式匹配, 按照替换规则, 编译时批处理

    - 宏定义

        ```rust
        macro_rules! swap {
            ($x:expr, $y:expr) => {
                {
                    let temp = $x;
                    $x = $y;
                    $y = temp;
                }
            };
        }
        
        ```

    - 宏调用
        ```rust
        let mut a = 5;
        let mut b = 10;
        swap!(a, b);
        ```

        

