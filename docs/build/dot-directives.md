---
title: "점 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE의 점 지시문"
  - "NMAKE 프로그램, 점 지시문"
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 점 지시문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

점 지시문은 설명 블록 외부에서 줄의 시작에 지정합니다.  점 지시문은 마침표\( . \)로 시작하고 뒤에 콜론\(:\)이 옵니다.  공백과 탭을 사용할 수 있습니다.  점 지시문 이름은 대\/소문자를 구분하며 대문자를 사용합니다.  
  
|지시문|용도|  
|---------|--------|  
|**.IGNORE :**|지시문이 지정된 위치에서 메이크파일의 끝까지 명령이 반환한0이 아닌 종료 코드를 무시합니다.  기본적으로 명령이 0이 아닌 종료 코드를 반환하면 NMAKE가 중지됩니다.  오류 확인을 복원하려면 **\!CMDSWITCHES**를 사용합니다.  단일 명령에 대한 종료 코드를 무시하려면 대시\(–\) 한정자를 사용합니다.  파일 전체에 대한 종료 코드를 무시하려면 \/I를 사용합니다.|  
|**.PRECIOUS :** *targets*|*targets*를 업데이트할 명령이 중지되는 경우 디스크에 *targets*를 보존합니다. 명령이 파일을 삭제하여 인터럽트를 처리하는 경우에는 적용되지 않습니다.  공백이나 탭을 하나 이상 사용하여 대상 이름을 구분합니다.  기본적으로 Ctrl\+C 또는 Ctrl\+Break를 사용하여 빌드를 중단하면 NMAKE가 대상을 삭제합니다.  **.PRECIOUS**를 지정할 때마다 메이크파일 전체에 지시문이 적용됩니다. 이 지시문을 여러 번 지정하면 적용이 누적됩니다.|  
|**.SILENT :**|지시문이 지정된 위치에서 메이크파일의 끝까지 실행된 명령을 표시하지 않습니다.  기본적으로 NMAKE는 명령이 호출될 때 화면에 표시합니다.  화면 표시를 복원하려면 **\!CMDSWITCHES**를 사용합니다.  단일 명령을 화면에 표시하지 않으려면 **@** 한정자를 사용합니다.  전체 파일을 화면에 표시하지 않으려면 \/S를 사용합니다.|  
|**.SUFFIXES :** `list`|유추 규칙과 일치하는 확장명을 나열합니다. 확장명으로 .exe .obj .asm .c .cpp .cxx .bas .cbl .for .pas .res .rc .f .f90이 미리 정의되어 있습니다.|  
  
 **.SUFFIXES** 목록 순서를 변경하거나 새 목록을 지정하려면 목록을 취소하고 새 설정을 지정합니다.  콜론 뒤에 확장명을 지정하지 않으면 목록이 취소됩니다.  
  
```  
.SUFFIXES :  
```  
  
 목록 끝에 다른 접미사를 추가하려면 다음과 같이 지정합니다.  
  
```  
.SUFFIXES : suffixlist  
```  
  
 여기에서 *suffixlist*는 추가된 접미사의 목록이며 하나 이상의 공백이나 탭으로 구분됩니다.  **.SUFFIXES**의 현재 설정을 표시하려면 \/P를 적용하여 NMAKE를 실행합니다.  
  
## 참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)