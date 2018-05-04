---
title: -sdl (추가 보안 검사 사용) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa984b488f74043b8c90876047516ebca23d4d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="sdl-enable-additional-security-checks"></a>/SDL(추가 보안 검사 사용)
권장되는 SDL(Security Development Lifecycle) 검사를 추가합니다. 이러한 검사에는 오류와 같은 추가 보안 관련 경고 및 추가 보안 코드 생성 기능이 포함됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
/sdl[-]  
```  
  
## <a name="remarks"></a>설명  
 **/sdl** 에서 제공 하는 기준 보안 검사 보다 더 [/GS](../../build/reference/gs-buffer-security-check.md) 재정의 **/GS-** 합니다. 기본적으로 **/sdl** 꺼져 있습니다. **/sdl-** 추가 보안 검사를 비활성화 합니다.  
  
## <a name="compile-time-checks"></a>컴파일 시간 검사  
 **/sdl** 이러한 경고를 오류로 활성화 합니다.  
  
|/SDL에 의해 활성화된 경고|해당 명령줄 스위치|설명|  
|------------------------------|-------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|단항 빼기 연산자가 부호 없는 형식에 적용되어 부호 없는 결과가 발생했습니다.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|음의 정수 상수가 부호 없는 형식으로 변환되어 의미 없는 결과가 발생할 수 있습니다.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|사용 하 여 `continue`, `break` 또는 `goto` 의 키워드는 `__finally` / `finally` 블록 비정상적으로 종료 하는 동안 동작이 정의 되지 않았습니다.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|변수를 초기화 하는 코드가 실행되지 않습니다.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|초기화되지 않은 지역 변수 사용.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|잠재적으로 초기화되지 않은 지역 포인터 변수 사용.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|특정 CRT(C 런타임) 함수를 사용할 때 버퍼가 오버런됩니다.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Pragma로 표시 된 함수를 사용 [사용 되지 않는](../../preprocessor/deprecated-c-cpp.md)합니다.|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|함수를 사용으로 표시 된 [사용 되지 않는](../../cpp/deprecated-cpp.md)합니다.|  
  
## <a name="runtime-checks"></a>런타임 검사  
 때 **/sdl** 가 활성화 컴파일러 런타임 시 이러한 검사를 수행 하는 코드를 생성 합니다.  
  
-   Strict 모드를 사용 하면 **/GS** 런타임 버퍼 오버런 검색을 사용 하 여 컴파일하면 해당 `#pragma strict_gs_check(push, on)`합니다.  
  
-   제한된 포인터 삭제를 수행합니다. 역참조를 포함하지 않으며 사용자 정의된 소멸자가 없는 식에서 포인터 참조는 `delete`에 대한 호출 이후 유효하지 않은 주소로 설정됩니다. 이렇게 하면 오래된 포인터 참조가 재사용되지 않습니다.  
  
-   클래스 멤버 초기화를 수행합니다. 개체 인스턴스화 시(생성자 실행 전) 모든 클래스 멤버를 자동으로 0으로 초기화합니다. 이렇게 하면 생성자가 명시적으로 초기화하지 않는 클래스 멤버와 연관된 초기화되지 않은 데이터를 사용하지 않도록 방지할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 [경고, /sdl 및 초기화 되지 않은 변수 검색 향상](http://go.microsoft.com/fwlink/p/?LinkId=331012)합니다.  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  에 **일반** 페이지에서 옵션을 선택 합니다는 **SDL 검사** 드롭 다운 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)