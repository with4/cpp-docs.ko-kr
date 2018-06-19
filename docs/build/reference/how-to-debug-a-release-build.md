---
title: '방법: 릴리스 빌드 디버깅 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e733375f01d4b2b8ec7090f7f70ad1ec5280cd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374481"
---
# <a name="how-to-debug-a-release-build"></a>방법: 릴리스 빌드 디버깅
응용 프로그램의 릴리스 빌드를 디버그할 수 있습니다.  
  
### <a name="to-debug-a-release-build"></a>릴리스 빌드를 디버깅 하려면  
  
1.  열기는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **C/c + +** 노드. 설정 **디버깅 정보 형식** 를 [C7 호환 되는 (/ Z7)](../../build/reference/z7-zi-zi-debug-information-format.md) 또는 **프로그램 데이터베이스 (/Zi)** 합니다.  
  
3.  확장 **링커** 클릭는 **일반** 노드. 설정 **증분 링크 사용** 를 [아니요 (/ /INCREMENTAL: NO)](../../build/reference/incremental-link-incrementally.md)합니다.  
  
4.  선택 된 **디버깅** 노드. 설정 **디버그 정보 생성** 를 [예 (/debug)](../../build/reference/debug-generate-debug-info.md)합니다.  
  
5.  선택 된 **최적화** 노드. 설정 **참조** 를 [/opt: ref](../../build/reference/opt-optimizations.md) 및 **COMDAT 정리 사용** 를 [/opt: icf](../../build/reference/opt-optimizations.md)합니다.  
  
6.  이제 릴리스 빌드 응용 프로그램을 디버깅할 수 있습니다. 에 오류가 발생 한 위치를 찾을 때까지 문제, 코드 (또는 시간에서 마법사를 사용 하 여 디버깅)를 단계별로 발견 하 고 잘못 된 매개 변수 또는 코드를 확인 합니다.  
  
     디버그 빌드에서 작동 하는 응용 프로그램에서 릴리스 빌드를 실패 한 경우 소스 코드에서 결함이 있는 경우일 수 컴파일러 최적화 기능 중 하나입니다. 이 문제를 격리 하려면 문제를 일으키는 되는 최적화와 파일을 찾을 때까지 각 소스 코드 파일에 대 한 선택한 최적화를 비활성화 합니다. (프로세스를 촉진 하기 위해 파일을 두 그룹으로 나누는, 하나의 그룹에서 최적화를 사용 하지 않도록 설정 있고 그룹에서 문제를 발견 하는 경우 문제가 있는 파일을 격리 될 때까지 계속 합니다.)  
  
     사용할 수 있습니다 [/RTC](../../build/reference/rtc-run-time-error-checks.md) 디버그 빌드에서 이러한 버그를 노출 하려고 합니다.  
  
     자세한 내용은 참조 [코드 최적화](../../build/reference/optimizing-your-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)