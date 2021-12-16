CREATE DATABASE yogesh
create table covid(
   date  INT              NOT NULL,
   cases VARCHAR (20)     NOT NULL,
   death  INT              NOT NULL,
   
);

;INSERT INTO public.covid(
	"STATE")
	VALUES ('aasaam');
  
  --for import the csv file data
copy public.covid191 from 'C:\Users\yogesh joshi\Desktop'  with csv header;



  Exporting CRUD functions in a PostgreSQL REST API
  module.exports = {
  getUsers,
  getUserById,
  createUser,
  updateUser,
  deleteUser,
}


Here is our complete queries.js file.

const Pool = require('pg').Pool
const pool = new Pool({
  user: 'me',
  host: 'localhost',
  database: 'api',
  password: 'password',
  port: 5432,
})


const getUserById = (request, response) => {
  const {date} = parseInt(request.params.date)

  pool.query('SELECT * FROM covid191 WHERE date = 2-02-19', [date], (error, results) => {
    if (error) {
      throw error
    }
    response.status(200).json(results.rows)
  })
}
const getUserById = (request, response) => {
  const {cases} = parseInt(request.params.cases)

  pool.query('SELECT * FROM covid191 WHERE date = 2-02-19', [cases], (error, results) => {
    if (error) {
      throw error
    }
    response.status(200).json(results.rows)
  })
}

const createUser = (request, response) => {
  const {  death } = request.body

  pool.query('INSERT INTO covid191 ( death) VALUES (50, 2)', [death], (error, results) => {
    if (error) {
      throw error
    }
    response.status(201).send(`User added with ID: ${result.insertId}`)
  })
}


}

module.exports = {
  getUsers,
  getUserById,
  createUser,
  updateUser,
  deleteUser,
