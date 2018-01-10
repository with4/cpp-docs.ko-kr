---
title: tlbid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tlbid
dev_langs: C++
helpviewer_keywords: tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 812b105fc02782b611b3f55061e448062dcd07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tlbid"></a>tlbid
**C + + 전용**  
  
 기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `number`  
 `filename`에 있는 형식 라이브러리의 수입니다.  
  
## <a name="remarks"></a>설명  
 다중 형식 라이브러리가 단일 DLL에 빌드된 경우 `tlbid`를 사용하여 기본 형식 라이브러리 이외의 라이브러리를 로드할 수 있습니다.  
  
 예:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 다음과 동일합니다.  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)