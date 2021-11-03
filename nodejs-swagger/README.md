https://github.com/swagger-api/swagger-ui  
swagger-ui github 페이지에서 소스 다운로드

프로젝트 폴더에 정적 파일을 불러올수 있도록 public 폴더 생성
public 폴더에 다운로드 받은 swagger-ui 의 dist 폴더를 복사  
dist 폴더의 폴더 이름을 docs 로 변경

swagger 명세서를 변경하기 위해서  
public > swagger.yaml 파일 생성

```yaml
openapi: 3.0.0
info:
  version: '1.0.0'
  title: 'My API'
  description: 'My API'
servers:
  - description: My API
    url: http://localhost:3000/
paths:
  /adder:
    get:
      summary: Adder API
      parameters:
        - name: one
          in: query
          description: First Value
          required: true
          schema:
            type: integer
        - name: two
          in: query
          description: Second Value
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Added Result
          schema:
            type: integer
```

docs 폴더로 가서 index.html 페이지의  
default url 경로 인 petstore.swagger.io/v2/swagger.json 을 localhost:3000 으로 변경  
오류가 나면 https -> http 로 변경

Unable to render this definition 메시지가 뜨는 경우
swagger.yaml 파일 경로를 정확히 적어준다.
url 경로 => http://localhost:3000/swagger.yaml
