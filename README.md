# gofibergorm

- @Param page query string false "page"
- @Param per_page query string false "per_page"
- @Param sort query string false "Сортировка asc/desc" Enums(asc, desc)
- @Param sort_field query string false "Поля для сортировки через запятую"
- @Param filter_values query string false "Значение поля для фильтрации, через запятую"
- @Param filter_fields query string false "Название полей для фильтрации, через запятую"
- @Param filter_type query string false "Тип фильтра полное совпадение (=) или совпадение по like" Enums(=, like)
- @Param filter_logic query string false "Пересечение или дополнение" Enums(and, or)

http://exmaple.com?page=1&per_page=250&sort=asc&sort_field=name&filter_values=hello%20world&filter_fields=name&filter_type=%3D

Result json:

```go
type PaginationResult struct {
    Page    int         `json:"page"`
    PerPage int         `json:"perPage"`
    Count   int64       `json:"count"`
    Items   interface{} `json:"items"`
}
```