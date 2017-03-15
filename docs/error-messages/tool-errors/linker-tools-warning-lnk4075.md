---
title: "링커 도구 경고 LNK4075 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
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
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 84dea754a1d2268c92e703dd04b0169ccc258ab3
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4075"></a>링커 도구 경고 LNK4075
"option1" "option2" 사양으로 인해 무시  
  
 두 번째 옵션은 첫 번째를 재정의합니다.  
  
 상호 배타적인 링커 옵션 지정 됩니다.  링커 옵션을 확인 합니다.  링커 옵션을 지정 하는 프로젝트를 빌드하는 방법에 따라 달라 집니다.  
  
-   개발 환경에서 작성 하는 경우 프로젝트에 대 한 링커 속성 페이지에서 찾아서 링커 옵션을 모두 지정 된 위치를 참조 하십시오.  참조 [프로젝트 속성](../../ide/working-with-project-properties.md) 에 대 한 자세한 내용은 합니다.  
  
-   명령줄에서 빌드하는 경우 여기에 지정 된 링커 옵션을 찾습니다.  
  
-   빌드 스크립트를 빌드하는 경우이 링커 옵션 지정 된 위치를 참조 하 여 스크립트를 확인 합니다.  
  
 상호 배타적인 링커 옵션을 지정 하는 위치를 발견 하면 링커 옵션 중 하나를 제거 합니다.  
  
 몇 가지 구체적인 예제:  
  
-   으로 컴파일된 모듈을 연결 하는 경우 **/ZI**, 의미 없는 /EDITANDCONTINUE /EDITANDCONTINUE, 및 /opt: ref, /opt: icf, 또는 /incremental: no, 컴파일된 모듈 이라는 내부 링커 옵션을 의미 있는, LNK4075를 받게 됩니다.  참조 [/Z7, /Zi, /ZI (디버깅 정보 형식)](../../build/reference/z7-zi-zi-debug-information-format.md) 에 대 한 자세한 내용은 합니다.
