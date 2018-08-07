---
title: '방법: 전역 어셈블리 캐시에 네이티브 DLL 추가 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7363de172eabc664bcde1e3bf42f8cc499e4251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129540"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>방법: 전역 어셈블리 캐시에 네이티브 DLL 추가
네이티브 DLL COM이 아닌 전역 어셈블리 캐시에 넣을 수 있습니다.  
  
## <a name="example"></a>예제  
 **/ASSEMBLYLINKRESOURCE** 어셈블리에 네이티브 DLL을 포함할 수 있습니다.  
  
 자세한 내용은 [/ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)를 참조하세요.  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)