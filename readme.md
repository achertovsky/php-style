# prerequisites
Personal authors styleguide that serves as public manifestation of following obligation attempts. Does not conflicts with [PSR-2](https://www.php-fig.org/psr/psr-2/). Its in public space for sharing reason. <br>
_If you mind i have it and you dont - [just create own](https://github.com/new)_

# accepted
- If class method or standalone function (default php ofc, you not into [procedural programming](https://en.wikipedia.org/wiki/Procedural_programming), aint u?) has more than one parameter - pass every parameter from new line, including first
    ```
    $string = 'foo';
    //right
    strpos(
        $string,
        'bar'
    );
    is_string($string);

    //wrong
    strpos($string, 'bar');
    is_string(
        $string
    );
    ```

# staging
- if instance contains chain of calls after it - every have to be on new line. Semicolon should be on new line after chain over, aligned with instance
  ```
    class Foo {
        public function bar(): void
        {
            //right
            $this
                ->sleep()
                ->sleep()
            ;
            $this->sleep();

            //wrong
            $this->sleep()->sleep();
            $this
                ->sleep()
            ;
        }

        public function sleep(): void
        {
            sleep(1);
        }
    }

    class Bar
    {
        private Foo $foo;

        function __construct() {
            $this->foo = new Foo();
        }

        public function bar(): void
        {
            //right
            $this->foo
                ->sleep()
                ->sleep()
            ;
            $this->foo->sleep();
            //wrong you may get, aint u?
        }
    }

    //right
    $instance = (new Foo())
        ->sleep()
        ->sleep()
    ;
    (new Foo())->sleep();
    $instance
        ->sleep()
        ->sleep()
    ;
    $instance->sleep();
    //wrong you may get, aint u?
  ```
- If method (constructor, etc) contains more than 1 param - every param should be placed at own, new line
  ```
    interface A {
        public function a(string $param): void; //right
        public function b(
            string $param
        ): void; // wrong
    }
    interface B {
        public function a(
            string $param,
            string $param2
        ): void; //right
        public function b(string $param, string $param2): void; //wrong
    }
  ```
