---
title: "링커 도구 경고 LNK4075 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8c3330e637ae0e0dce5e875fcc349c6deefcf27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4075"></a>링커 도구 경고 LNK4075
"option1" "옵션 2" 사양으로 인해 무시합니다.  
  
 두 번째 옵션은 첫 번째를 재정의합니다.  
  
 상호 배타적인 링커 옵션이 지정 됩니다.  링커 옵션을 확인 합니다.  링커 옵션을 지정 하는 프로젝트를 빌드하는 방법에 따라 달라 집니다.  
  
-   개발 환경에서 작성 하는 경우 프로젝트에 대 한 링커 속성 페이지의 모양과 링커 옵션을 모두 지정 된 위치를 참조 하십시오.  참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md) 자세한 정보에 대 한 합니다.  
  
-   명령줄에서 빌드하는 경우 여기에 지정 된 링커 옵션을 찾습니다.  
  
-   빌드 스크립트를 빌드하는 경우 스크립트에서이 링커 옵션 지정 된 위치를 참조 하도록를 조사 합니다.  
  
 상호 배타적인 링커 옵션을 지정 하는 위치를 찾았으면 링커 옵션 중 하나를 제거 합니다.  
  
 몇 가지 구체적인 예제:  
  
-   으로 컴파일된 모듈을 연결 하는 경우 **/ZI**, 의미 없는 /EDITANDCONTINUE /EDITANDCONTINUE, 및 /opt: ref, /opt: icf, 또는 /incremental: no,으로 컴파일된 모듈 호출 내부 링커 옵션을 의미 하는 LNK4075를 가져옵니다.  참조 [/Z7, /Zi, /ZI (디버깅 정보 형식)](../../build/reference/z7-zi-zi-debug-information-format.md) 자세한 정보에 대 한 합니다.