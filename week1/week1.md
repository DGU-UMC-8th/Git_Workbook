1. 공식 사이트 읽기 - 안드로이드 api 레퍼런스

    i. Essentials
        1) AI 환경 빌드
        2) 시작하기
            a) 튜토리얼
            b) Kotlin: 문법
        3) 기기별 확장
        4) 카테고리별 빌드
        5) news

    ii. Design 및 계획
        1) Ui 디자인
        2) 아키텍처
        3) 품질
        4) 보안
        5) 빌드

    iii. Develop
        1) 더보기: gemini, 핵심 영역, 도구 및 워크플로, 기기 기술, 라이브러리
        2) 개요
        3) 코드 샘플, 플젝 샘플
        4) 가이드
        5) API 참조

    iv. Google play: 구글 플레이 콘솔 (앱 등록, 배포, 관리)

    v. 커뮤니티

    vi. Android studio: 다운로드, 업데이트, 유저 가이드
    
2. 레이아웃 구성 결정
    1) Linear: 단순한 수직 또는 수평 정렬
        a. 예시 코드
        <LinearLayout
            xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical"
            android:padding="16dp">
         
            <TextView
                android:id="@+id/tv_title"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="감정우표 선택"
                android:textSize="20sp"
                android:textStyle="bold"/>
         
            <ImageView
                android:id="@+id/img_stamp"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:src="@drawable/emotion_stamp"
                android:layout_gravity="center"/>
         
            <Button
                android:id="@+id/btn_next"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="다음 화면으로 이동"
                android:layout_gravity="center"
                android:onClick="goToNextScreen"/>
        </LinearLayout>
        ➡ 장점: 단순한 구조에서는 LinearLayout이 사용하기 편리
        ➡ 단점: 요소가 많아지면 Nested LinearLayout이 필요하여 비효율적
                     
    2) Constraint: 복잡하고 여러 ui 요소 포함하거나 뷰 간 관계가 중요
        a. 예시코드
        <androidx.constraintlayout.widget.ConstraintLayout
            xmlns:android="http://schemas.android.com/apk/res/android"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:padding="16dp">
         
            <TextView
                android:id="@+id/tv_title"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="감정우표 선택"
                android:textSize="20sp"
                android:textStyle="bold"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintTop_toTopOf="parent"/>
         
            <ImageView
                android:id="@+id/img_stamp"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:src="@drawable/emotion_stamp"
                app:layout_constraintTop_toBottomOf="@id/tv_title"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintEnd_toEndOf="parent"/>
         
            <Button
                android:id="@+id/btn_next"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="다음 화면으로 이동"
                app:layout_constraintTop_toBottomOf="@id/img_stamp"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintEnd_toEndOf="parent"
                android:onClick="goToNextScreen"/>
        </androidx.constraintlayout.widget.ConstraintLayout>
        ➡ 장점: 다양한 화면 크기에 대응하기 좋고, 복잡한 UI도 효율적으로 관리 가능
        ➡ 단점: 단순한 구조에서는 코드가 다소 길어질 수 있음
3. 정리

| **항목** | **LinearLayout** | **ConstraintLayout** |
| --- | --- | --- |
| **구조** | 단순한 수직/수평 정렬 | 제약을 사용한 유연한 배치 |
| **레이아웃 중첩** | 중첩이 많아질수록 비효율적 | 하나의 레이아웃으로 복잡한 구조 지원 |
| **성능** | 중첩이 많으면 성능 저하 가능 | 상대적으로 더 빠른 성능 |
| **화면 대응** | 다양한 화면 크기에 대응이 어려움 | 다양한 해상도에 적응 가능 |
| **코드 길이** | 단순한 경우 코드가 짧음 | 복잡한 UI에도 깔끔한 코드 유지 |

**✅ 결론:**

- 단순한 UI는 LinearLayout이 적합
- 복잡한 UI, 다양한 해상도 지원 필요 시 ConstraintLayout 사용 권장