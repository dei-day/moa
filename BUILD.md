# 소스와 빌드

Release의 `moa-source-0.8.6.zip`을 압축 해제합니다. 앱 소스, 리소스, 테스트, Gradle Wrapper, 빌드 설정과 폰트 라이선스가 포함됩니다. 로컬 메모 데이터·인증 정보·서명 키·모델 파일·빌드 캐시는 포함하지 않습니다.

## 개발 환경

- JDK 17 이상 (기존 검증은 Android Studio 내장 JDK 사용)
- Android SDK 35
- Gradle 8.9 (Wrapper 제공)
- Kotlin / Jetpack Compose

`local.properties`에 본인의 Android SDK 경로를 지정한 뒤 실행합니다.

```sh
chmod +x gradlew
./gradlew assembleDebug testDebugUnitTest
```

APK 위치: `app/build/outputs/apk/debug/app-debug.apk`

앱 패키지: `com.foldnotes` · minSdk 28 · targetSdk 35. 최소 설치 OS와 음성 전사·내장 AI의 지원 조건은 다릅니다. 각 기능의 실제 사용 가능 여부는 기기에서 확인해야 합니다.

## 배포 시 유의점

현재 제공 APK는 기존 개발 환경의 Android Debug 인증서로 서명되었습니다. 새 환경에서 빌드하면 서명이 달라 기존 APK 위에 업데이트 설치하지 못할 수 있습니다. 배포용 서명 체계를 정할 때 이 점을 고려해야 합니다. 서명 키는 이 저장소에 포함하지 않습니다.

내장 AI·다운로드 모델의 실기기 호환성과 품질은 별도로 검증해야 합니다. 소스 공개 또는 재배포 라이선스는 아직 지정하지 않았습니다. 번들 폰트의 라이선스는 `design/licenses`를 참고하세요.
