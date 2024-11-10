# HomeWorkMsq-04.11.2024
USE hr;

SELECT e1.job_id
FROM employees e1
JOIN employees e2 ON e1.manager_id = e2.employee_id
WHERE e1.salary > e2.salary;


SELECT e.first_name, e.last_name, l.city
FROM employees e
JOIN departments d ON e.department_id = d.department_id
JOIN locations l ON d.location_id = l.location_id
WHERE l.city IN ('Seattle', 'Toronto');


SELECT e.first_name, e.last_name, e.salary
FROM employees e
JOIN departments d ON e.department_id = d.department_id
JOIN locations l ON d.location_id = l.location_id
WHERE l.city IN ('Oxford', 'San Francisco');


SELECT e.first_name, e.last_name, l.city
FROM employees e
JOIN departments d ON e.department_id = d.department_id
JOIN locations l ON d.location_id = l.location_id;


SELECT l.city, c.country_name
FROM locations l
JOIN countries c ON l.country_id = c.country_id;



SELECT d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.department_id
WHERE e.salary > 10000
  AND e.employee_id IN (
      SELECT DISTINCT manager_id
      FROM employees
      WHERE manager_id IS NOT NULL
  );
