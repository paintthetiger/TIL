






Scalability Session # 200220
- MySQL indice
	Clustered Index - B+ tree 구조. leaf 노드에 row의 값이 담겨 있음. primary key로 이루어진 index
	
	Secondary Index - primary key 이외의 column으로 만들어짐. leaf에서 primary key가 붙어 있음. 이후 다시 Cluster Index에 가서 찾아야 함.

	Compostie Index - 두개 이상의 column의 붙여서 만든 Index. cardinality와 자주 쓰이는 것을 고려해서 순서를 정해야 한다.
	
	Covering Index - 필요힌 필드를 포함해서 인덱스를 만드는 경우. 이 경우는 Cluster Index를 다시 찾을 필요가 없어서 극도의 최적화를 하는데 용이하다.

	Adaptive Hash Index - primary key -> 데이터 를 연결하는 해시형태의 인덱스. 보통은 모든 primary key에 대해서 값을 다 가지고 있지는 않고 sparse 하게 가지고 있다. Inno DB의 옵션으로 사용된다. 다만 table을 drop 하거나 truncate 하게 되면 이 기능 때문에 DB 전체의 성능이 매우 떨어지는 경우가 있다. (이로부터 미루어 봤을때 아마 전체 table이 모두 공유하는 것 같기도 하다.)

    *Redshift는 MySQL 완전히 다른 스키마를 가지고 있다.













