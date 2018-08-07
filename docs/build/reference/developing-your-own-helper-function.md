---
title: 사용자 도우미 함수 개발 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6b8e397fecc8f14140cd7c86217421d5aa1a749
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371400"
---
# <a name="developing-your-own-helper-function"></a>사용자 도우미 함수 개발
고유한 버전의 DLL 이나 가져오기 이름을 기반으로 하는 특정 처리를 수행 하는 루틴을 제공 하려는 경우. 이 작업을 수행 하는 방법은 두 가지가: 후크 설명한 알림 후크를 사용 하 여 제공 된 버전 또는 코딩을 직접 제공된 된 코드에 기반 합니다.  
  
 코드 작성  
 새 인증서에 대 한 지침으로 제공된 된 코드를 기본적으로 사용할 수 있으므로이 과정이 매우 간단 합니다. 물론, 호출 규칙을 따라야 합니다 및 링커 생성 한 썽크를 반환 하는 경우 적절 한 함수 포인터를 반환 해야 합니다. 한 번 코드에서 호출에서 나가기 또는 호출을 충족 하기 위해 원하는 작업이 무엇이 든 거의 수행할 수 있습니다.  
  
 알림 후크 처리 시작을 사용 하 여  
 아마도 가장 쉬운 dlistartprocessing 알림의 기본 도우미와 동일한 값을 받는 알림 사용자가 제공한 후크 함수에 대 한 새 포인터를 제공 하기만 하면 됩니다. 해당 시점에 후크 함수를 사용 하는 기본 도우미의 모든 추가 처리가 기본 도우미 제어가 반환을 무시 하는 대로 기본적으로 새 도우미 함수를 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)