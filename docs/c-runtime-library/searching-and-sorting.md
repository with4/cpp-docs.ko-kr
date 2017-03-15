---
title: "검색 및 정렬 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- sorting data
- data [CRT], searching
- searching [C++], CRT search functions
- searching [C++]
ms.assetid: 15e984f0-e155-46f5-8542-51c458792f54
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 5ba605d61ddcf1ae6bd2adc24c41737536fa2ce9
ms.lasthandoff: 02/24/2017

---
# <a name="searching-and-sorting"></a>검색 및 정렬
검색 및 정렬을 위해 다음 함수를 사용합니다.  
  
### <a name="searching-and-sorting-functions"></a>검색 및 정렬 함수  
  
|함수|검색 또는 정렬|.NET Framework의 해당 값|  
|--------------|--------------------|-------------------------------|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|이진 검색|[System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[bsearch_s](../c-runtime-library/reference/bsearch-s.md)|`bsearch`의 보다 안전한 버전입니다.|[System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[_lfind](../c-runtime-library/reference/lfind.md)|지정된 값에 대한 선형 검색|[System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[_lfind_s](../c-runtime-library/reference/lfind-s.md)|`_lfind`의 보다 안전한 버전입니다.|[System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[_lsearch](../c-runtime-library/reference/lsearch.md)|지정된 값에 대한 선형 검색. 찾을 수 없으면 배열에 추가됩니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_lsearch_s](../c-runtime-library/reference/lsearch-s.md)|`_lsearch`의 보다 안전한 버전입니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[qsort](../c-runtime-library/reference/qsort.md)|빠른 정렬|[System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
|[qsort_s](../c-runtime-library/reference/qsort-s.md)|`qsort`의 보다 안전한 버전입니다.|[System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
