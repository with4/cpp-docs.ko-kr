---
title: "등록 기관 코드 (c + + 전용)에 대 한 정적 링크가 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>등록 기관 코드 (c + + 전용)에 대 한 정적 링크가 설정
C + + 클라이언트 등록자의 코드에 정적 링크를 만들 수 있습니다. 릴리스 빌드로 5k 약 추가 등록자의 파서를 정적으로 연결 합니다.  
  
 정적 연결을 설정 하는 가장 간단한 방법은 사용자가 지정한 가정 [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) 개체의 선언에 있습니다. (이 ATL에서 사용 되는 기본 사양은)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID를 사용 하 여 정적 링크를 만들려면  
  
1.  지정 [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D 대신**_ATL_DLL**합니다.  
  
2.  다시 컴파일하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [레지스트리 구성 요소 (등록자)](../atl/atl-registry-component-registrar.md)

