---
title: "점 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9958b13a6f06b0024ec2d4dd304abfe93b16741e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dot-directives"></a>점 지시문
점 지시문은 줄의 시작 부분에 설명 블록 외부를 지정 합니다. 점 지시문은 마침표로 시작 (합니다. )에 콜론 (:) 뒤에 야 합니다. 공백 및 탭 허용 됩니다. 점 지시문 이름은 대 소문자를 구분 하며 대문자입니다.  
  
|지시문|용도|  
|---------------|-------------|  
|**. 무시:**|메이크파일의의 끝에 지정 된 위치에서 명령에 의해 반환 되는 0이 아닌 종료 코드를 무시 합니다. 기본적으로 NMAKE 명령 0이 아닌 종료 코드를 반환 하는 경우 중지 됩니다. 오류 검사를 복원 하려면 사용 **! CMDSWITCHES**합니다. 단일 명령에 대 한 종료 코드를 무시 하려면 대시 (-) 한정자를 사용 합니다. 전체 파일에 대 한 종료 코드를 무시 하려면 사용 하 여 / I.|  
|**. 귀중:** *대상*|유지 *대상* 디스크의 경우이 정보도 업데이트 명령을 중지 됩니다; 아무 효과가 명령 파일을 삭제 하 여 인터럽트를 처리 하는 경우. 대상 이름을 하나 이상의 공백이 나 탭으로 구분 합니다. 기본적으로 NMAKE 빌드 CTRL + C 또는 CTRL + BREAK 중단 된 경우 대상을 삭제 합니다. 각각의 사용 **합니다. 소중한** 전체 메이크파일;에 적용 됩니다 여러 사양 누적 되어 증가 합니다.|  
|**. 자동:**|메이크파일의의 끝에 지정 된 위치에서 실행 된 명령 표시를 하지 않습니다. 기본적으로 NMAKE 명령이 호출 될를 표시 합니다. 사용 하 여 에코 복원 **! CMDSWITCHES**합니다. 단일 명령을 에코를 표시 하지 않으려면 사용는  **@**  한정자입니다. 전체 파일에 대 한 화면 표시 하지 않으려면을 사용 하 여/s.|  
|**. 접미사:**`list`|유추 규칙 일치;에 대 한 확장 나열 다음 확장을 포함 하도록 미리 정의 된:.exe.obj.asm.c.cpp.cxx.bas.cbl에 대해.pas.res.rc.f.f90|  
  
 변경 하 여 **합니다. 접미사** 목록 순서 또는 새 목록을 지정 하려면 목록 선택을 취소 하 고 새 설정을 지정 합니다. 목록을 지우려면 콜론 뒤에 확장 없음를 지정 합니다.  
  
```  
.SUFFIXES :  
```  
  
 목록의 끝에 추가 접미사를 추가 하려면 지정  
  
```  
.SUFFIXES : suffixlist  
```  
  
 여기서 *suffixlist* 는 하나 이상의 공백이 나 탭으로 구분 된 추가 된 접미사 목록이 나와 있습니다. 현재 설정을 보려면 **합니다. 접미사**를 사용 하십시오.를 사용 하 여 NMAKE 실행  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)