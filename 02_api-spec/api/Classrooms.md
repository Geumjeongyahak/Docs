# Classroom API

## 1. 분반 목록 조회
- **URL**: `/api/v1/classrooms`
- **Method**: `GET`
- **Authorization**: 인증 필요
- **Description**: 페이지네이션된 분반 목록을 조회합니다.
- **Query Parameters**:
    - `page` (optional): 페이지 번호 (0-based)
    - `size` (optional): 페이지 크기
- **Response**: `ApiResponse<BasePageResponse<ClassroomResponse>>`

## 2. 분반 상세 조회
- **URL**: `/api/v1/classrooms/{id}`
- **Method**: `GET`
- **Authorization**: 인증 필요
- **Description**: ID로 분반을 조회합니다.
- **Response**: `ApiResponse<ClassroomResponse>`

## 3. 분반 생성
- **URL**: `/api/v1/classrooms`
- **Method**: `POST`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 새로운 분반을 생성합니다.
- **Request Body**:
    ```json
    {
      "name": "벚꽃반",
      "type": "WEEKDAY"
    }
    ```
- **Response**: `ApiResponse<ClassroomResponse>`

## 4. 분반 수정
- **URL**: `/api/v1/classrooms/{id}`
- **Method**: `PUT`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 분반 정보를 수정합니다.
- **Request Body**:
    ```json
    {
      "name": "장미반",
      "type": "WEEKEND"
    }
    ```
- **Response**: `ApiResponse<ClassroomResponse>`

## 5. 분반 삭제
- **URL**: `/api/v1/classrooms/{id}`
- **Method**: `DELETE`
- **Authorization**: `hasRole('ADMIN')`
- **Description**: 분반을 삭제합니다.
- **Response**: `ApiResponse<Void>`
