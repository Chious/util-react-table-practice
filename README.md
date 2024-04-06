# Util: react-table Practice

## Dependencies

- [react-table](https://tanstack.com/table/v7/) - Headless UI for table
- [data-fns](https://date-fns.org) -- Modern JS date utility library

## Get Started

```
npm install
npm run dev
```

## How to use react-table ?

1. Create table info(`columns.jsx` for example):

```js
export const COLUMNS = [
  {
    Header: "Id",
    Footer: "Id",
    accessor: "id",
    Filter: ColumnFilter,
    disableFilters: true,
  },
  {
    Header: "First Name",
    Footer: "First Name",
    accessor: "first_name",
    Filter: ColumnFilter,
  },
];
```

2. Create Table Instance(see `BasicTable`):

```js
import { useTable } from "react-table";

const columns = useMemo(() => COLUMNS, []);
const data = useMemo(() => MOCK_DATA, []);

const {
  getTableProps,
  getTableBodyProps,
  headerGroups,
  footerGroups,
  rows,
  prepareRow,
} = useTable({
  columns: columns,
  data: data,
});
```

3. Hooks is supported for customize method:

- useSortBy: for sorting(see: `SortTable.jsx`)
- usePagination: for Pagination(see: `PaginationTable.jsx`)
- useGlobalFilter, useFilters: for filter(see: `FilteringTable.jsx`)

## Reference

1. This code is copy from [React Table Tutorial](https://www.youtube.com/watch?v=YwP4NAZGskg&list=PLC3y8-rFHvwgWTSrDiwmUsl4ZvipOw9Cz&index=1)

2. Fake data created by [mockaroo](https://www.mockaroo.com)
