---
title: "프로젝트 빌드 오류 PRJ0003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bcf80eb4d45fe1ae163772b96339c123996ae377
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="project-build-error-prj0003"></a>프로젝트 빌드 오류 PRJ0003  
  
> 오류를 생성할 '*명령줄*'.  
  
*명령줄* 명령 형식에 입력에서 파생 된 **속성 페이지** 대화 상자는 오류 코드를 반환 했지만에 아무 정보도 표시는 **출력** 창.  

이 오류에 대 한 가능한 원인은 다음과 같습니다.  
  
-   프로젝트에 ATL 서버에 따라 달라 집니다. Visual Studio 2008부터, ATL 서버를 더 이상 Visual Studio의 일부로 포함 있지만 CodePlex에서 공유 원본 프로젝트로 서 놓았습니다. ATL 서버 소스 코드 및 도구를 다운로드 하려면로 이동 [ATL 서버 라이브러리 및 도구](http://go.microsoft.com/fwlink/p/?linkid=81979)합니다.  
  
-   시스템 리소스가 부족 합니다. 이 문제를 해결할 일부 응용 프로그램을 닫습니다.  
  
-   보안 권한이 부족 합니다. 보안 권한이 충분 한지 확인 합니다.  
  
-   에 지정 된 실행 파일 경로 **VC + + 디렉터리** 실행을 시도 하는 도구에 대 한 경로 포함 하지 않습니다. 자세한 내용은 참조 하세요. [프로젝트 속성 사용](../../ide/working-with-project-properties.md)  
  
-   실행할 명령이 없습니다 메이크파일 프로젝트에 대 한 **빌드 명령줄** 또는 **다시 빌드 명령줄**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 빌드 오류 및 경고(PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)