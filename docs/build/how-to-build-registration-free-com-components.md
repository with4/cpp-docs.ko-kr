---
title: "방법: 등록이 필요 없는 COM 구성 요소를 만들 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 018a3ba707f4c5cff73b5a5c54f82400a79a8d46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-registration-free-com-components"></a>방법: 등록이 필요 없는 COM 구성 요소 빌드
등록이 필요 없는 COM 구성 요소는 Dll에 내장 된 매니페스트에 있는 COM 구성 요소.  
  
### <a name="to-build-manifests-into-com-components"></a>COM 구성 요소에 매니페스트를 빌드  
  
1.  COM 구성 요소에 대 한 프로젝트 속성 페이지를 엽니다.  
  
2.  확장의 **구성 속성** 노드를 확장 한 후의 **매니페스트 도구** 노드.  
  
3.  선택 된 **입력 및 출력** 속성 페이지를 제거한 다음 설정의 **매니페스트 포함** 속성에 **예**.  
  
4.  **확인**을 클릭합니다.  
  
5.  솔루션을 빌드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [격리 된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)   
 [Side-by-side-어셈블리에 대 한](http://msdn.microsoft.com/library/ff951640)   
 [방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드](../build/how-to-build-isolated-applications-to-consume-com-components.md)