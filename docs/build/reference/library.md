---
title: "라이브러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LIBRARY
dev_langs: C++
helpviewer_keywords: LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71637c83eda0ee641a4b66d94ba113162baa7bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="library"></a>LIBRARY
링크는 DLL을 만드는를 알려 줍니다. 같은 시간에 링크 빌드에서.exp 파일 사용 되지 않은 경우 가져오기 라이브러리를 만듭니다.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## <a name="remarks"></a>설명  
 *라이브러리* 인수 DLL의 이름을 지정 합니다. 사용할 수도 있습니다는 [/out](../../build/reference/out-output-file-name.md) 링커 옵션을 DLL의 출력 이름을 지정 합니다.  
  
 기본 =*주소* 인수 운영 체제를 사용 하 여 DLL을 로드할 기본 주소를 가져오거나 설정 합니다. 이 인수는 0x10000000의 기본 DLL 위치를 재정의합니다. 에 대 한 설명을 참조는 [/base](../../build/reference/base-base-address.md) 기준 주소에 대 한 세부 정보에 대 한 옵션입니다.  
  
 사용 해야는 [/DLL](../../build/reference/dll-build-a-dll.md) DLL을 빌드할 때 링커 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)