---
title: 컴파일러 오류 C2241 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d1a4404d3f7e60adc2d8f9ff0c8ccb3d154b26d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2241"></a>컴파일러 오류 C2241
'identifier': 멤버 액세스가 제한됩니다.  
  
 코드가 전용 또는 보호된 멤버에 액세스하려고 합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면  
  
1.  멤버의 액세스 수준을 변경합니다.  
  
2.  멤버를 액세스하는 함수의 `friend` 로 선언합니다.