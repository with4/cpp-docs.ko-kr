---
title: "링커 도구 오류 LNK2005 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf93f364b3dc7156a62eb1c474177eb7b85c7827
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2005"></a>링커 도구 오류 LNK2005
개체에 이미 정의된 기호  
  
데코레이팅된 폼으로 표시되는 해당 `symbol` 기호는 여러 번 정의되었습니다.  
  
자세한 내용은 다음 기술 자료 문서를 참조하세요.  
  
-   [CRT 라이브러리와 MFC 라이브러리는 Visual c + +에서 잘못 된 순서로 연결 된 경우 LNK2005 오류 발생](https://support.microsoft.com/kb/148652)  
  
-   [FIX: 오버 로드 된 전역 Delete 연산자 원인 LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Visual c + +에서 ATL 실행 파일 (.exe) 프로젝트를 컴파일하는 경우 LNK2005 오류를 수신](https://support.microsoft.com/kb/184235)합니다.  
  
이 오류는 심각한 오류 다음 [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md)합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  사용 하는 경우 정적 및 동적 라이브러리를 혼합 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
2.  기호는 패키지 함수 (사용해 컴파일하여 만든 [/Gy](../../build/reference/gy-enable-function-level-linking.md)) 하 고 둘 이상의 파일에 포함 되어 있지만 컴파일 간에 변경 되었습니다. `symbol`이 포함된 모든 파일을 다시 컴파일합니다.  
  
3.  다른 라이브러리에 있는 두 멤버 개체의 기호가 다르게 정의되었고 두 멤버 개체 모두 사용되었습니다.  
  
4.  각 정의에서 다른 값을 사용하여 절대 값이 두 번 정의되었습니다.  
  
5.  헤더 파일이 변수를 선언 및 정의합니다. 가능한 해결 방법은 다음과 같습니다.  
  
    -   h에서 변수를 선언(`extern BOOL MyBool;`)한 다음 .c 또는 .cpp 파일에서 이 변수에 값을 할당합니다(`BOOL MyBool = FALSE;`).  
  
    -   변수 선언 [정적](../../cpp/storage-classes-cpp.md#static)합니다.  
  
    -   변수 선언 [selectany](../../cpp/selectany.md)합니다.  
  
6.  GUID를 정의하는 다른 .lib 파일(예: oledb.lib 및 adsiid.lib)과 함께 uuid.lib를 사용하는 경우, 예:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     를 해결 하려면 추가 [/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) 링커 명령줄 옵션 및 있는지 확인 하려면 다음 uuid.lib가 참조 하는 첫 번째 라이브러리입니다.
