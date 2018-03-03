---
title: "방법: 전역 어셈블리 캐시에 네이티브 DLL 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be55fd47cd6024d0660ed0c3e4594c9430f80cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>방법: 전역 어셈블리 캐시에 네이티브 DLL 추가
네이티브 DLL COM이 아닌 전역 어셈블리 캐시에 넣을 수 있습니다.  
  
## <a name="example"></a>예  
 **/ASSEMBLYLINKRESOURCE** 어셈블리에 네이티브 DLL을 포함할 수 있습니다.  
  
 자세한 내용은 [/ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)를 참조하세요.  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)