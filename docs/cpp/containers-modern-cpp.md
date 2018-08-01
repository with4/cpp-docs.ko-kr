---
title: 컨테이너 (최신 c + +) | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d740bb36c1d574e474058c05d900d605c71e55f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406336"
---
# <a name="containers-modern-c"></a>컨테이너(최신 C++)

기본적으로 사용 하 여 [벡터](../standard-library/vector-class.md) c + +에서 기본 순차 컨테이너로 합니다. 이 설정은 `List<T>` .NET 언어에서입니다.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

사용 하 여 [지도](../standard-library/map-class.md) (없습니다 `unordered_map`) 기본 연관 컨테이너로 합니다. 사용 하 여 [설정할](../standard-library/set-class.md)를 [multimap](../standard-library/multimap-class.md), 및 [multiset](../standard-library/multiset-class.md) 중복 제거 및 다중 사례에 대 한 합니다.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

성능 최적화, 필요할 때 사용 하는 것이 좋습니다.

- 합니다 [배열](../standard-library/array-class-stl.md) 포함 하는 것이 중요 클래스 멤버로 예를 들어을 입력 합니다.

- 연관 컨테이너와 같은 순서가 지정 되지 않은 [unordered_map](../standard-library/unordered-map-class.md)합니다. 이러한 요소 마다 낮은 오버 헤드 있고 일정 시간 조회 되지만 있을 수 있습니다 정확 하 고 효율적으로 사용 하기 어렵습니다.

- 정렬 `vector`합니다. 자세한 내용은 [알고리즘](../cpp/algorithms-modern-cpp.md)을 참조하세요.

C 스타일 배열을 사용 하지 마세요. 직접 데이터에 대 한 액세스가 필요한 이전 api를 사용 하 여 접근자 메서드 같은 `f(vec.data(), vec.size());` 대신 합니다.

컨테이너에 대 한 자세한 내용은 참조 하세요. [c + + 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)합니다.

## <a name="see-also"></a>참고자료
 [C++의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)  
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)  