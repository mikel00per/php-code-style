## 👀 How to use

1. Install the dependency
    ```sh
    composer require --dev mikelooper/coding-style
    ```
2. Add it to your `ecs.php` file:
    ```php
    use CodelyTv\CodingStyle;
    use Symplify\EasyCodingStandard\Config\ECSConfig;

    return function (ECSConfig $ecsConfig): void {
        $ecsConfig->paths([__DIR__ . '/src',]);

        $ecsConfig->sets([CodingStyle::DEFAULT]);

        // Or this if you prefer to have the code aligned
        // $ecsConfig->sets([CodingStyle::ALIGNED]);
    };
    ```
3. Execute it:
    ```sh
    ./vendor/bin/ecs check
    ```

## 🤔 What it does

- Lints PHP using PSR-12
- Extends some config (you can see all the rules [here](src/coding_style.php))
- Use tabs to indent ([reason](https://www.youtube.com/watch?v=yD2T42zsP7c)). If you want to use spaces, you can add the
  following line at the end of your `ecs.php`:
    ```php
    use Symplify\EasyCodingStandard\ValueObject\Option;

	$ecsConfig->indentation(Option::INDENTATION_SPACES);
    ```
