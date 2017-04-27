---
title: "링커 도구 오류 LNK1104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 7fce9c60da4bceafb9ee81231a8630acb4397d83
ms.lasthandoff: 04/24/2017

---
# <a name="linker-tools-error-lnk1104"></a>링커 도구 오류 LNK1104
파일을 열 수 없습니다 '*filename*'  
  
링커 지정된 된 파일을 열 수 없습니다.  
  
이 오류를 해결 하려면 다음과 같은 가능한 원인을 확인 합니다.  
  
-   파일 *filename* 존재 하지 않습니다. 이 파일을 생성 하기 위해 다른 프로젝트에 종속 되는 프로젝트, 프로젝트 종속성 올바르게 설정 되어 있는지 확인 합니다.  
  
-   프로젝트의 속성 페이지 대화 상자에서 라이브러리를 지정할 때 라이브러리 이름은 쉼표가 아닌 공백을 사용 하 여 구분 되어야 합니다.  
  
-   파일 이름 또는 명령줄에 지정 된 경로가 올바르지 않거나 경로 잘못 된 드라이브 지정 합니다. 맞춤법을 확인 하 고 파일 이름 및 위치를 확인 합니다. 다른 컴퓨터에서 복사 된 프로젝트를 작성 하는 경우에 경로 확인는 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md) 하 고 필요에 따라 업데이트 합니다.  
  
-   프로젝트 구성 또는 플랫폼 도구 집합에 대 한 라이브러리가 설치 되지 않습니다. 플랫폼 도구 집합 및 프로젝트에 대 한 속성 페이지에 지정 하는 Windows SDK 설치 되어 있고 도구 집합 및 구성 설정에 필요한 라이브러리를 포함 되었는지 확인 합니다. 하나 빌드의 작동 하는 경우 오류가 발생 하면 다른 설정이 올바른지, 그리고 두 구성 모두에 대 한 필요한 도구가 설치 되어 있는지 확인 하므로, 디버그 및 소매 구성에 대 한 별도 설정이 있습니다.  
  
-   디스크 공간이 필요가 없습니다. 비정상적인 링커 링크 하는 동안 임시 디스크 공간을 많이 사용할 수는 없습니다.  
  
-   에 액세스 하려면 부족 한 파일 권한이 *filename*합니다.  
  
-   에 대 한 경로 *filename* 최대 260 자가 하를 확장 합니다. 이름을 변경 하거나 필요한 파일의 경로를 단축 하는 데 필요한 경우 디렉터리 구조를 다시 정렬 합니다.  
  
-   경우는 *filename* LNK 라는*n*, 임시 파일의 링커에 의해 생성 된 파일 이름인 TMP 환경 변수에 지정 된 디렉터리가 존재 하지 않을 수 있습니다, 또는 둘 이상의 디렉터리가 TMP 환경 변수에 대해 지정할 수 있습니다. TMP 환경 변수에 대해 하나의 디렉터리 경로만 지정 해야 합니다.  
  
-   라이브러리 이름에 대해 오류 메시지가 발생하고, 이전 Microsoft Visual C++ 개발 시스템에서 .mak 파일을 최근에 포팅한 경우 라이브러리가 더 이상 유효하지 않을 수 있습니다. 라이브러리 이름은 올바른 이며 지정된 된 위치에 있는지 확인 하거나 새 위치를 가리키도록 LIB 경로 업데이트 합니다.  
  
-   다른 프로그램에서 파일을 열어서 링커에서 해당 파일에 쓸 수 없습니다. 바이러스 백신 프로그램 종종 일시적으로 차단 새로 만든된 파일에 대 한 액세스. 바이러스 백신 검사 프로그램에서 프로젝트 빌드 디렉터리를 제외 해 보십시오.  
  
-   잘못 된 LIB 환경 변수를 만들어야합니다. LIB 환경 변수를 업데이트 하는 방법에 대 한 정보를 참조 하십시오. [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md)합니다. 필요한 라이브러리가 포함된 디렉터리 목록이 여기에 있는지 확인합니다.  
  
-   링커는 여러 사례에서 임시 파일을 사용합니다. 충분 한 디스크 공간이 있는 경우에 매우 큰 링크 상당 부분 사용 하거나 사용 가능한 디스크 공간을 조각 수 있습니다. 사용 하는 것이 좋습니다는 [/OPT (최적화)](../../build/reference/opt-optimizations.md) 옵션; 수행 전이적 comdat 제거 읽기 모든 개체 파일 여러 번입니다.
