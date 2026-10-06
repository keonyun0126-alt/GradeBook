# 성적 계산 프로그램 (패키지 구조)

이 프로그램은 학생들의 점수를 입력받아 각 학생의 평균 점수와 학점을 계산하고, 전체 반의 평균 점수를 출력합니다. 패키지 구조로 확장하여 모듈화, CSV 파일 입출력, CLI 실행 및 단위 테스트 기능을 제공합니다.

# 주요 기능

* 학생 별 평균 점수 계산
* 평균 점수에 따른 학점 부여 (A, B, C, D, F)
* 전체 반의 평균 점수 계산 및 출력
* CSV 파일(`students.csv`)로부터 학생 성적 데이터 읽기 및 저장
* 패키지 단위 직접 실행 (CLI 지원)
* `unittest` 기반의 유닛 테스트 제공

# 코드 구성

* `utils.py`: 성적 계산 관련 유틸리티 함수
  * `mean(scores)`: 점수 리스트를 받아 평균을 계산하는 함수
  * `letter_grade(score)`: 평균 점수에 따라 학점을 반환하는 함수
* `models.py`: 학생 및 성적부 클래스
  * `Student` 클래스: 학생 이름과 점수를 저장하고, 평균 및 학점 계산 메서드 포함
  * `GradeBook` 클래스: 여러 학생 객체를 관리하고 전체 반 평균을 계산
* `io/csvio.py`: CSV 파일 입출력 모듈
  * `load_students_from_csv(path)`: CSV 파일에서 학생 정보를 읽어오는 함수
  * `save_students_to_csv(path, students)`: 학생 데이터를 CSV 파일로 저장하는 함수
* `cli.py`: 명령행 인터페이스(CLI) 실행 함수(`run_cli`) 포함
* `__main__.py`: 패키지를 직접 실행할 수 있도록 진입점 제공
* `tests/test_utils.py`: `utils.py`의 함수들을 테스트하는 유닛 테스트 클래스

# 실행 방법

```bash
python -m gradebook