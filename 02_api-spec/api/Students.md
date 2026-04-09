# Student API

## 1. 학생 목록 조회
- **URL**: `/api/v1/students`
- **Method**: `GET`
- **Authorization**: 인증 필요
- **Description**: 페이지네이션된 학생 목록을 조회합니다.
- **Query Parameters**:
    - `page` (optional): 페이지 번호 (0-based)
    - `size` (optional): 페이지 크기
- **Response**: `ApiResponse<BasePageResponse<StudentResponse>>`

## 2. 학생 상세 조회
- **URL**: `/api/v1/students/{id}`
- **Method**: `GET`
- **Authorization**: 인증 필요
- **Description**: ID로 학생을 조회합니다.
- **Response**: `ApiResponse<StudentResponse>`

## 3. 학생 생성
- **URL**: `/api/v1/students`
- **Method**: `POST`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 새로운 학생을 생성합니다.
- **Request Body**:
    ```json
    {
      "name": "김학생",
      "phoneNumber": "010-1234-5678"
    }
    ```
- **Response**: `ApiResponse<StudentResponse>`

## 4. 학생 수정
- **URL**: `/api/v1/students/{id}`
- **Method**: `PUT`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 학생 정보를 수정합니다.
- **Request Body**:
    ```json
    {
      "name": "박학생",
      "phoneNumber": "010-9876-5432"
    }
    ```
- **Response**: `ApiResponse<StudentResponse>`

## 5. 학생 삭제
- **URL**: `/api/v1/students/{id}`
- **Method**: `DELETE`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 학생을 삭제합니다.
- **Response**: `ApiResponse<Void>`
