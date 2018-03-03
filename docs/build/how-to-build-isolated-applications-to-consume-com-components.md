---
title: "방법: COM 구성 요소를 사용 하는 격리 된 응용 프로그램 빌드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaeef56f122d10f983313ab1c839db40f4e92aa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드
격리 된 응용 프로그램은 프로그램에서 기본 제공 매니페스트가 있는 응용 프로그램. COM 구성 요소를 사용 하는 격리 된 응용 프로그램을 만들 수 있습니다.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>격리 된 응용 프로그램의 매니페스트에 COM 참조를 추가 하려면  
  
1.  격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.  
  
2.  확장의 **구성 속성** 노드를 확장 한 후의 **매니페스트 도구** 노드.  
  
3.  선택은 **격리 COM** 속성 페이지를 제거한 다음 설정의 **구성 요소 파일 이름** 속성을 원하는 격리 된 응용 프로그램이 COM 구성 요소 이름입니다.  
  
4.  **확인**을 클릭합니다.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>격리 된 응용 프로그램에 매니페스트를 빌드  
  
1.  격리 된 응용 프로그램에 대 한 프로젝트 속성 페이지를 엽니다.  
  
2.  확장의 **구성 속성** 노드를 확장 한 후의 **매니페스트 도구** 노드.  
  
3.  선택 된 **입력 및 출력** 속성 페이지를 제거한 다음 설정의 **매니페스트 포함** 속성에 **예**.  
  
4.  **확인**을 클릭합니다.  
  
5.  솔루션을 빌드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [격리 된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)   
 [Side-by-side-어셈블리에 대 한](http://msdn.microsoft.com/library/ff951640)