**REST API 란?**

RESPT API란 REST의 원리를 따르는 API를 의미합니다.
하지만 REST API를 올바르게 설계하기 위해서는 지켜야 하는 몇가지 규칙이 있다.

1. URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 한다.

> Bad Example http://khj93.com/Running/ <br>
> Good Example  http://khj93.com/run/

2. 마지막에 슬래시 (/)를 포함하지 않는다.

> Bad Example http://khj93.com/test/ <br>
> Good Example  http://khj93.com/test

3. 언더바 대신 하이폰을 사용한다.

> Bad Example http://khj93.com/test_blog <br>
> Good Example  http://khj93.com/test-blog

4. 파일확장자는 URI에 포함하지 않는다.

> Bad Example http://khj93.com/photo.jpg  <br>
> Good Example  http://khj93.com/photo

5. 행위를 포함하지 않는다.

> Bad Example http://khj93.com/delete-post/1  <br>
> Good Example http://khj93.com/post/1  