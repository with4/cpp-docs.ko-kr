---
title: "컴파일러 오류 C2241 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2241
dev_langs: C++
helpviewer_keywords: C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7bbd320e93150d163db78f4fd089c319d30cbfd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2241"></a>컴파일러 오류 C2241
'identifier': 멤버 액세스가 제한됩니다.  
  
 코드가 전용 또는 보호된 멤버에 액세스하려고 합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>다음 해결 방법을 사용하여 수정하려면  
  
1.  멤버의 액세스 수준을 변경합니다.  
  
2.  멤버를 액세스하는 함수의 `friend` 로 선언합니다.