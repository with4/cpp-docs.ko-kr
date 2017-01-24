---
title: "/sdl(추가 보안 검사 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.SDLCheck"
dev_langs: 
  - "C++"
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /sdl(추가 보안 검사 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

권장되는 SDL\(Security Development Lifecycle\) 검사를 추가합니다.  이러한 검사에는 오류와 같은 추가 보안 관련 경고 및 추가 보안 코드 생성 기능이 포함됩니다.  
  
## 구문  
  
```  
/sdl[-]  
```  
  
## 설명  
 **\/sdl**은 [\/GS](../../build/reference/gs-buffer-security-check.md)에서 제공되는 기준 보안 검사의 상위 집합을 활성화하고 **\/GS\-**를 재정의합니다.  기본적으로 **\/sdl**는 OFF로 설정됩니다.  **\/sdl\-**은 추가 보안 검사를 비활성화합니다.  
  
## 컴파일 시 검사  
 **\/sdl**은 다음과 같은 경고를 오류로 활성화합니다.  
  
|\/sdl에 의해 활성화된 경고|해당 명령줄 스위치|설명|  
|-----------------------|----------------|--------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|\/we4146|단항 빼기 연산자가 부호 없는 형식에 적용되어 부호 없는 결과가 발생했습니다.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|\/we4308|음의 정수 상수가 부호 없는 형식으로 변환되어 의미 없는 결과가 발생할 수 있습니다.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|\/we4532|`continue`\/`break` 블록에서 `goto`, `__finally` 또는 `finally` 키워드를 사용하면 비정상 종료 시 정의되지 않은 동작이 발생합니다.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|\/we4533|변수를 초기화 하는 코드가 실행되지 않습니다.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|\/we4700|초기화되지 않은 지역 변수 사용.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|\/we4703|잠재적으로 초기화되지 않은 지역 포인터 변수 사용.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|\/we4789|특정 CRT\(C 런타임\) 함수를 사용할 때 버퍼가 오버런됩니다.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|\/we4995|[사용되지 않는](../../preprocessor/deprecated-c-cpp.md) Pragma로 표시된 함수 사용.|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|\/we4996|[사용되지 않는](../../cpp/deprecated-cpp.md) 것으로 표시된 함수 사용.|  
  
## 런타임 검사  
 **\/sdl**이 활성화된 경우 컴파일러가 이러한 검사를 런타임에 수행하기 위한 코드를 생성합니다.  
  
-   **\/GS**로 컴파일할 때와 동일한 `#pragma strict_gs_check(push, on)` 런타임 버퍼 오버런 검색에 대해 strict 모드를 활성화합니다.  
  
-   제한된 포인터 삭제를 수행합니다.  역참조를 포함하지 않으며 사용자 정의된 소멸자가 없는 식에서 포인터 참조는 `delete`에 대한 호출 이후 유효하지 않은 주소로 설정됩니다.  이렇게 하면 오래된 포인터 참조가 재사용되지 않습니다.  
  
-   클래스 멤버 초기화를 수행합니다.  개체 인스턴스화 시\(생성자 실행 전\) 모든 클래스 멤버를 자동으로 0으로 초기화합니다.  이렇게 하면 생성자가 명시적으로 초기화하지 않는 클래스 멤버와 연관된 초기화되지 않은 데이터를 사용하지 않도록 방지할 수 있습니다.  
  
## 설명  
 자세한 내용은 [경고, \/sdl 및 초기화되지 않은 변수 검색 향상](http://go.microsoft.com/fwlink/p/?LinkId=331012)\(영문\)을 참조하세요.  
  
#### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **일반** 페이지의 **SDL 검사** 드롭다운 목록에서 옵션을 선택합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)