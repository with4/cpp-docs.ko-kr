---
title: "링커 도구 오류 LNK2005 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2005"
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체에 이미 정의된 기호  
  
 데코레이팅된 폼으로 표시되는 해당 `symbol` 기호는 여러 번 정의되었습니다.  
  
 자세한 내용은 다음 기술 자료 문서를 참조하세요.  
  
-   "링크 C 런타임 라이브러리가 MFC 라이브러리보다 먼저 연결된 경우 LNK2005 오류"\(Q148652\)  
  
-   "전역 오버로드된 delete 연산자로 인해 LNK2005 발생"\(Q140440\)  
  
-   "\_ATL\_MIN\_CRT 정의 시 new 및 delete에 대한 LNK2005 오류"\(Q184235\)  
  
 기술 자료 문서는 MSDN 라이브러리 CD\-ROM 또는 [http:\/\/support.microsoft.com\/search](http://support.microsoft.com/search)에 있습니다.  
  
 이 오류는 심각한 [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md) 오류가 발생한 후 나타납니다.  
  
### 다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용하는 경우 정적 및 동적 라이브러리를 혼합합니다.  
  
2.  기호는 [\/Gy](../../build/reference/gy-enable-function-level-linking.md)를 사용해 컴파일하여 만든 패키지 함수로, 두 개 이상의 파일에 포함되어 있지만 컴파일 간에 변경되었습니다.  `symbol`이 포함된 모든 파일을 다시 컴파일합니다.  
  
3.  다른 라이브러리에 있는 두 멤버 개체의 기호가 다르게 정의되었고 두 멤버 개체 모두 사용되었습니다.  
  
4.  각 정의에서 다른 값을 사용하여 절대 값이 두 번 정의되었습니다.  
  
5.  헤더 파일이 변수를 선언 및 정의합니다.  가능한 해결 방법은 다음과 같습니다.  
  
    -   h에서 변수를 선언\(`extern BOOL MyBool;`\)한 다음 .c 또는 .cpp 파일에서 이 변수에 값을 할당합니다\(`BOOL MyBool = FALSE;`\).  
  
    -   변수를 [정적](../../misc/static-cpp.md)으로 선언합니다.  
  
    -   변수를 [selectany](../../cpp/selectany.md)로 선언합니다.  
  
6.  GUID를 정의하는 다른 .lib 파일\(예: oledb.lib 및 adsiid.lib\)과 함께 uuid.lib를 사용하는 경우,  예를 들면 다음과 같습니다.  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     수정하려면 링커 명령줄 옵션에 [\/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md)을 추가한 다음 uuid.lib가 참조되는 첫 번째 라이브러리인지 확인합니다.