# User API

## 1. 사용자 목록 조회
- **URL**: `/api/v1/users`
- **Method**: `GET`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 페이지네이션된 사용자 목록을 조회합니다.
- **Query Parameters**:
    - `page` (optional): 페이지 번호 (0-based)
    - `size` (optional): 페이지 크기
- **Response**: `ApiResponse<BasePageResponse<UserResponse>>`

## 2. 사용자 상세 조회
- **URL**: `/api/v1/users/{id}`
- **Method**: `GET`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: ID로 사용자를 조회합니다.
- **Response**: `ApiResponse<UserResponse>`

## 3. 사용자 생성
- **URL**: `/api/v1/users`
- **Method**: `POST`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 사용자를 생성합니다.
- **Request Body**:
    ```json
    {
      "username": "user01",
      "name": "홍길동",
      "password": "password",
      "email": "user@example.com",
      "phoneNumber": "010-1234-5678"
    }
    ```
- **Response**: `ApiResponse<UserResponse>`

## 4. 사용자 수정
- **URL**: `/api/v1/users/{id}`
- **Method**: `PUT`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 사용자 정보를 수정합니다.
- **Request Body**:
    ```json
    {
      "name": "홍길동",
      "email": "updated@example.com",
      "phoneNumber": "010-9876-5432"
    }
    ```
- **Response**: `ApiResponse<UserResponse>`

## 5. 사용자 삭제
- **URL**: `/api/v1/users/{id}`
- **Method**: `DELETE`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 사용자를 삭제합니다.
- **Response**: `ApiResponse<Void>`

## 6. 사용자 역할 부여
- **URL**: `/api/v1/users/{id}/roles`
- **Method**: `POST`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 사용자에게 역할을 부여합니다.
- **Request Body**:
    ```json
    {
      "roleId": 3
    }
    ```
- **Response**: `ApiResponse<Void>`

## 7. 사용자 역할 제거
- **URL**: `/api/v1/users/{id}/roles/{roleId}`
- **Method**: `DELETE`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 사용자의 역할을 제거합니다.
- **Response**: `ApiResponse<Void>`
