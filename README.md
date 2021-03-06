
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Import required libraries and packages"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 87,
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Read a csv file as pandas DataFrame"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 88,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>model</th>\n",
       "      <th>year</th>\n",
       "      <th>price</th>\n",
       "      <th>transmission</th>\n",
       "      <th>mileage</th>\n",
       "      <th>fuelType</th>\n",
       "      <th>mpg</th>\n",
       "      <th>engineSize</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>5 Series</td>\n",
       "      <td>2014</td>\n",
       "      <td>11200</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>67068</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>57.6</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>6 Series</td>\n",
       "      <td>2018</td>\n",
       "      <td>27000</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>14827</td>\n",
       "      <td>Petrol</td>\n",
       "      <td>42.8</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>5 Series</td>\n",
       "      <td>2016</td>\n",
       "      <td>16000</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>62794</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>51.4</td>\n",
       "      <td>3.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>1 Series</td>\n",
       "      <td>2017</td>\n",
       "      <td>12750</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>26676</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>72.4</td>\n",
       "      <td>1.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>7 Series</td>\n",
       "      <td>2014</td>\n",
       "      <td>14500</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>39554</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>50.4</td>\n",
       "      <td>3.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10776</th>\n",
       "      <td>X3</td>\n",
       "      <td>2016</td>\n",
       "      <td>19000</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>40818</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>54.3</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10777</th>\n",
       "      <td>5 Series</td>\n",
       "      <td>2016</td>\n",
       "      <td>14600</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>42947</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>60.1</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10778</th>\n",
       "      <td>3 Series</td>\n",
       "      <td>2017</td>\n",
       "      <td>13100</td>\n",
       "      <td>Manual</td>\n",
       "      <td>25468</td>\n",
       "      <td>Petrol</td>\n",
       "      <td>42.8</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10779</th>\n",
       "      <td>1 Series</td>\n",
       "      <td>2014</td>\n",
       "      <td>9930</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>45000</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>64.2</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10780</th>\n",
       "      <td>X1</td>\n",
       "      <td>2017</td>\n",
       "      <td>15981</td>\n",
       "      <td>Automatic</td>\n",
       "      <td>59432</td>\n",
       "      <td>Diesel</td>\n",
       "      <td>57.6</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>10781 rows ?? 8 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "           model  year  price transmission  mileage fuelType   mpg  engineSize\n",
       "0       5 Series  2014  11200    Automatic    67068   Diesel  57.6         2.0\n",
       "1       6 Series  2018  27000    Automatic    14827   Petrol  42.8         2.0\n",
       "2       5 Series  2016  16000    Automatic    62794   Diesel  51.4         3.0\n",
       "3       1 Series  2017  12750    Automatic    26676   Diesel  72.4         1.5\n",
       "4       7 Series  2014  14500    Automatic    39554   Diesel  50.4         3.0\n",
       "...          ...   ...    ...          ...      ...      ...   ...         ...\n",
       "10776         X3  2016  19000    Automatic    40818   Diesel  54.3         2.0\n",
       "10777   5 Series  2016  14600    Automatic    42947   Diesel  60.1         2.0\n",
       "10778   3 Series  2017  13100       Manual    25468   Petrol  42.8         2.0\n",
       "10779   1 Series  2014   9930    Automatic    45000   Diesel  64.2         2.0\n",
       "10780         X1  2017  15981    Automatic    59432   Diesel  57.6         2.0\n",
       "\n",
       "[10781 rows x 8 columns]"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "df = pd.read_csv(\"bmw.csv\")\n",
    "\n",
    "display(df)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Check for missing values, data types of the columns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 89,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 10781 entries, 0 to 10780\n",
      "Data columns (total 8 columns):\n",
      " #   Column        Non-Null Count  Dtype  \n",
      "---  ------        --------------  -----  \n",
      " 0   model         10781 non-null  object \n",
      " 1   year          10781 non-null  int64  \n",
      " 2   price         10781 non-null  int64  \n",
      " 3   transmission  10781 non-null  object \n",
      " 4   mileage       10781 non-null  int64  \n",
      " 5   fuelType      10781 non-null  object \n",
      " 6   mpg           10781 non-null  float64\n",
      " 7   engineSize    10781 non-null  float64\n",
      "dtypes: float64(2), int64(3), object(3)\n",
      "memory usage: 673.9+ KB\n"
     ]
    },
    {
     "data": {
      "text/plain": [
       "None"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "display(df.info())"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Count the number of unique values present in the 'year' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 90,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "2019    3485\n",
       "2016    1882\n",
       "2017    1721\n",
       "2015     922\n",
       "2018     848\n",
       "2020     733\n",
       "2014     501\n",
       "2013     357\n",
       "2012     119\n",
       "2011      51\n",
       "2010      41\n",
       "2009      30\n",
       "2008      23\n",
       "2007      16\n",
       "2006      14\n",
       "2004      12\n",
       "2005       6\n",
       "2002       6\n",
       "1999       4\n",
       "2001       3\n",
       "2000       2\n",
       "2003       2\n",
       "1997       1\n",
       "1998       1\n",
       "1996       1\n",
       "Name: year, dtype: int64"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "year_count = df['year'].value_counts()\n",
    "display(year_count)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Count the number of unique values present in the 'model' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 91,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       " 3 Series    2443\n",
       " 1 Series    1969\n",
       " 2 Series    1229\n",
       " 5 Series    1056\n",
       " 4 Series     995\n",
       " X1           804\n",
       " X3           551\n",
       " X5           468\n",
       " X2           288\n",
       " X4           179\n",
       " M4           125\n",
       " 6 Series     108\n",
       " Z4           108\n",
       " X6           106\n",
       " 7 Series     106\n",
       " X7            55\n",
       " i3            43\n",
       " 8 Series      39\n",
       " M5            29\n",
       " M3            27\n",
       " M2            21\n",
       " i8            17\n",
       " M6             8\n",
       " Z3             7\n",
       "Name: model, dtype: int64"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "model_count = df['model'].value_counts()\n",
    "display(model_count)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Count the number of unique values present in the 'transmission' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 92,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Semi-Auto    4666\n",
       "Automatic    3588\n",
       "Manual       2527\n",
       "Name: transmission, dtype: int64"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "transmission_count = df['transmission'].value_counts()\n",
    "display(transmission_count)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Count the number of unique values present in the 'fuelType' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 93,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Diesel      7027\n",
       "Petrol      3417\n",
       "Hybrid       298\n",
       "Other         36\n",
       "Electric       3\n",
       "Name: fuelType, dtype: int64"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "fuelType_count = df['fuelType'].value_counts()\n",
    "display(fuelType_count)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Find the percentage of unique values present in the 'fuelType' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 94,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>fuel_type</th>\n",
       "      <th>No_of_cars</th>\n",
       "      <th>% of cars</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Diesel</td>\n",
       "      <td>7027</td>\n",
       "      <td>65.18</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Petrol</td>\n",
       "      <td>3417</td>\n",
       "      <td>31.69</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Hybrid</td>\n",
       "      <td>298</td>\n",
       "      <td>2.76</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Other</td>\n",
       "      <td>36</td>\n",
       "      <td>0.33</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Electric</td>\n",
       "      <td>3</td>\n",
       "      <td>0.03</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "  fuel_type  No_of_cars  % of cars\n",
       "0    Diesel        7027      65.18\n",
       "1    Petrol        3417      31.69\n",
       "2    Hybrid         298       2.76\n",
       "3     Other          36       0.33\n",
       "4  Electric           3       0.03"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "fuelType_count = df['fuelType'].value_counts()\n",
    "# print(type(fuelType_count))\n",
    "\n",
    "fuelType_count = pd.DataFrame(fuelType_count)\n",
    "# display(fuelType_count)\n",
    "\n",
    "fuelType_count = fuelType_count.reset_index()\n",
    "# display(fuelType_count)\n",
    "\n",
    "fuelType_count = fuelType_count.rename(columns={'index':'fuel_type', 'fuelType':'No_of_cars'})\n",
    "# display(fuelType_count)\n",
    "\n",
    "# print(fuelType_count['No_of_cars'].sum())\n",
    "\n",
    "fuelType_count['% of cars'] = np.round(((fuelType_count['No_of_cars']/fuelType_count['No_of_cars'].sum())*100), 2)\n",
    "display(fuelType_count)\n",
    "\n",
    "# print(type(fuelType_count))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Create a Barplot for the 'fuelType' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 95,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "sns.barplot(x='fuel_type', y='No_of_cars', data=fuelType_count, color='blue', alpha=0.75)\n",
    "plt.title(\"Number of cars present for each fuelType\")\n",
    "plt.xlabel(\"Type of fuel\")\n",
    "plt.ylabel(\"Number of cars\")\n",
    "# plt.grid()\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Find the percentage of unique values present in the 'transmission' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 96,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>transmission</th>\n",
       "      <th>No_of_cars</th>\n",
       "      <th>% of cars</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Semi-Auto</td>\n",
       "      <td>4666</td>\n",
       "      <td>43.28</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Automatic</td>\n",
       "      <td>3588</td>\n",
       "      <td>33.28</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Manual</td>\n",
       "      <td>2527</td>\n",
       "      <td>23.44</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "  transmission  No_of_cars  % of cars\n",
       "0    Semi-Auto        4666      43.28\n",
       "1    Automatic        3588      33.28\n",
       "2       Manual        2527      23.44"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "transmission_count = df['transmission'].value_counts()\n",
    "# print(type(transmission_count))\n",
    "\n",
    "transmission_count = pd.DataFrame(transmission_count)\n",
    "# display(transmission_count)\n",
    "\n",
    "transmission_count = transmission_count.reset_index()\n",
    "# display(transmission_count)\n",
    "\n",
    "transmission_count = transmission_count.rename(columns={'index':'transmission', 'transmission':'No_of_cars'})\n",
    "# display(transmission_count)\n",
    "\n",
    "# print(transmission_count['No_of_cars'].sum())\n",
    "\n",
    "transmission_count['% of cars'] = np.round(((transmission_count['No_of_cars']/transmission_count['No_of_cars'].sum())*100), 2)\n",
    "display(transmission_count)\n",
    "\n",
    "# print(type(transmission_count))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Create a Barplot for the 'transmission' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 97,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "sns.barplot(x='transmission', y='No_of_cars', data=transmission_count, color='blue', alpha=0.75)\n",
    "plt.title(\"Number of cars present for each transmission type\")\n",
    "plt.xlabel(\"Type of transmission\")\n",
    "plt.ylabel(\"Number of cars\")\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Find the percentage of unique values present in the 'model' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 98,
   "metadata": {
    "scrolled": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>model</th>\n",
       "      <th>No_of_cars</th>\n",
       "      <th>% of cars</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>3 Series</td>\n",
       "      <td>2443</td>\n",
       "      <td>22.66</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>1 Series</td>\n",
       "      <td>1969</td>\n",
       "      <td>18.26</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>2 Series</td>\n",
       "      <td>1229</td>\n",
       "      <td>11.40</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>5 Series</td>\n",
       "      <td>1056</td>\n",
       "      <td>9.80</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>4 Series</td>\n",
       "      <td>995</td>\n",
       "      <td>9.23</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>X1</td>\n",
       "      <td>804</td>\n",
       "      <td>7.46</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>6</th>\n",
       "      <td>X3</td>\n",
       "      <td>551</td>\n",
       "      <td>5.11</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7</th>\n",
       "      <td>X5</td>\n",
       "      <td>468</td>\n",
       "      <td>4.34</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>8</th>\n",
       "      <td>X2</td>\n",
       "      <td>288</td>\n",
       "      <td>2.67</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>9</th>\n",
       "      <td>X4</td>\n",
       "      <td>179</td>\n",
       "      <td>1.66</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10</th>\n",
       "      <td>M4</td>\n",
       "      <td>125</td>\n",
       "      <td>1.16</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11</th>\n",
       "      <td>6 Series</td>\n",
       "      <td>108</td>\n",
       "      <td>1.00</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>12</th>\n",
       "      <td>Z4</td>\n",
       "      <td>108</td>\n",
       "      <td>1.00</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>13</th>\n",
       "      <td>X6</td>\n",
       "      <td>106</td>\n",
       "      <td>0.98</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>14</th>\n",
       "      <td>7 Series</td>\n",
       "      <td>106</td>\n",
       "      <td>0.98</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>15</th>\n",
       "      <td>X7</td>\n",
       "      <td>55</td>\n",
       "      <td>0.51</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>16</th>\n",
       "      <td>i3</td>\n",
       "      <td>43</td>\n",
       "      <td>0.40</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>17</th>\n",
       "      <td>8 Series</td>\n",
       "      <td>39</td>\n",
       "      <td>0.36</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>18</th>\n",
       "      <td>M5</td>\n",
       "      <td>29</td>\n",
       "      <td>0.27</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>19</th>\n",
       "      <td>M3</td>\n",
       "      <td>27</td>\n",
       "      <td>0.25</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>20</th>\n",
       "      <td>M2</td>\n",
       "      <td>21</td>\n",
       "      <td>0.19</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>21</th>\n",
       "      <td>i8</td>\n",
       "      <td>17</td>\n",
       "      <td>0.16</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>22</th>\n",
       "      <td>M6</td>\n",
       "      <td>8</td>\n",
       "      <td>0.07</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>23</th>\n",
       "      <td>Z3</td>\n",
       "      <td>7</td>\n",
       "      <td>0.06</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "        model  No_of_cars  % of cars\n",
       "0    3 Series        2443      22.66\n",
       "1    1 Series        1969      18.26\n",
       "2    2 Series        1229      11.40\n",
       "3    5 Series        1056       9.80\n",
       "4    4 Series         995       9.23\n",
       "5          X1         804       7.46\n",
       "6          X3         551       5.11\n",
       "7          X5         468       4.34\n",
       "8          X2         288       2.67\n",
       "9          X4         179       1.66\n",
       "10         M4         125       1.16\n",
       "11   6 Series         108       1.00\n",
       "12         Z4         108       1.00\n",
       "13         X6         106       0.98\n",
       "14   7 Series         106       0.98\n",
       "15         X7          55       0.51\n",
       "16         i3          43       0.40\n",
       "17   8 Series          39       0.36\n",
       "18         M5          29       0.27\n",
       "19         M3          27       0.25\n",
       "20         M2          21       0.19\n",
       "21         i8          17       0.16\n",
       "22         M6           8       0.07\n",
       "23         Z3           7       0.06"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "model_count = df['model'].value_counts()\n",
    "# print(type(model_count))\n",
    "\n",
    "model_count = pd.DataFrame(model_count)\n",
    "# display(model_count)\n",
    "\n",
    "model_count = model_count.reset_index()\n",
    "# display(model_count)\n",
    "\n",
    "model_count = model_count.rename(columns={'index':'model', 'model':'No_of_cars'})\n",
    "# display(model_count)\n",
    "\n",
    "# print(model_count['No_of_cars'].sum())\n",
    "\n",
    "model_count['% of cars'] = np.round(((model_count['No_of_cars']/model_count['No_of_cars'].sum())*100), 2)\n",
    "display(model_count)\n",
    "\n",
    "# print(type(model_count))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Create a Barplot for the 'model' column"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 99,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAYkAAAEyCAYAAAAP0CwLAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMiwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy8vihELAAAACXBIWXMAAAsTAAALEwEAmpwYAAAksUlEQVR4nO3debwcVZn/8c+XJBDCkrA5gApRMYKgbAoYiSyibIILAQRlETdGVEZQ0HGEK8OwjYAiisgPBB0Mi7gCIQgIJAQiAlkIm+APFyLjAgEDBEjyzB/nNJSdru6+ndv39u3+vl+venX16XOqnurq7qdrO6WIwMzMrJaVhjoAMzPrXE4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJHqUpJB0YuH5xZL2GIDpHi7ptBWdToN57CJpvqTp7ZxPp5G0s6S3lLw25O+JpD5JRw7i/O6QNL7O6ztLumyw4ulWThK962ngMEljhjqQCkkjm6x6IPDvETFpkOc7KNOpY2egZpKgn+/JIMRqXcJJonc9B1wFfLT6BUmPShqdx1/aMpB0s6QzJN0t6U5Jb5F0o6TfSdq7MIlNJN0q6SFJH8xtR0k6N7e7p7LVkv99fkfSTcB/VcWxnqRrJc2VNE3Sv0g6FDgAOEvSOVX1K/OYJ2mOpD1z+dWS7pJ0r6QDc9n4vBzfA+6StIGk2yTNzvPbtGra43PcP5L0gKQzS6ZTtpwHSrovx3VlLltD0qW57ixJ2+byiyV9I5fdL2krSRsCRwJfzjG+oRDbP70nksZImpKX4zZJEwrTPUvSLcBRVcu3gaSfS/qNpFskvTaXH5njmyvpB5XkImmzXG9O/kc/Kk9qW0kzJD0i6d01PluHS7o8f24elfReSd/My3lhod5H8vq6V9InctkISRfkupcDKxfqf7wQ55eq52srICI89OAAPA5sCDwIjAQuBvbIrz0KjM7jhwOn5fGbSf9WAc4G7gBGA1sCMwv1HwZWB9YFHsnjnwI+m+usA9wHCOgDbgVG1Yjx28DRefxTwAV5/KVYq+p/Gvhenq6Acbl87fy4JjAfGAWMB5YAm+fXjgW+msdHAatWTXs8sBTYHBgB3ARMqjGdsuWcB7wml4/Nj2cA++bx1wKzCst3YR7fD7g0j/cBR5asz+L6Ow44O4/vBfyyUOeHJe0vA7bK4+8AflR87/L4OcCBefxOYJc8Pq6wLq/P78+2wG015nM4MJeXPzfPAhNz+7uACcArgYeAscAawAP5fT4AuDJPZ8u8PsYDWwCXk/70jsgxvIm05XXZUH/XhvvgTc4eFhELJM0g7apo1tX5cV6aRCyWNA/YqFBnWkQsAhZJmk36Er8TeKOkI3Kd1YF/yeM/i4gXa8xrIumHB+B/gM80iG1X4IzIvyLAwvz4b5Lem8c3Bl4FBHB/RMzP5b8BvidpCekH8v4a03+gUl/ST4C3k35ci9MpW86ZwHclXQr8uFB3d0kn5efjCvP6eX68B/hcg+WuNhE4BSAirpV0QeG1q0ra7AJsKqny/Nn8uKWk/yT9YI8FnpS0JrBGRPwqz2MhQG57TUQslXQP6b2u5YbC52ZxRMzM7eeTPker5zpP5fJrge2BtwFX5HnOkfRAIfaJwN35+erA64EnSt8ha5qThP03MAWYUyhbysu7Ilepqv9CflxWGY+IZfrnfdzVHYIF6Z/iRys/CBX5h+WZkthUY1r1LFdf0i7ADsD2+YfpLtIyLS7ONyJukfQOYB/gJ5KOiogbayxHrefF+MuW80jSj9w+wJ2SNs9194yIBTWW5fn8uIz+f0/rvW9l7/UyYJuIWFZVfgGwd0Q8KOkzpH/51Jn+81DzM1FU/Ny8UCivLGt1/Kp6rFV+XkSc8k8vSjuXzN/6wcckelxEPEDavfTOQvHvga0krUTaXdFfe0haXdK6wFakXTw3AP+ap4mkLZuYzm3AB/P4wcCMBvVvBD6hl40j7WJ6IieIrYA312ooaWPgzxFxHunf6ptqVNtM0uZ5Gd5P2jqoVracr8mJ48ukfelr5LovHRuQVDO2gkW5XSMvvW/5mMh9TbSZTj4+JWmlnMQAxgD/K2mVyjQj4mnSVuJOuf44FTZBBsCvgd0krSlpdWAPYBZpuQ7I89wSqByXuQn4YF7fSNpY0tgBjKenOUkYwOmkXTAVJwOXkH50H29herOAn5B+RL+cdz2dD/wFmJN3K3yhien0AXtJmgt8APiPBvXPJ/2TnQfMJv1zvw4Yl3d7HUfa713LzsDcvJtkImn3VrXZwPF5+vdERK3TTcuW88y8e2UucFFEPAmcBLwyH2y9D/hQg+W7GjhUVQeuazgX2DC/b1+h6iB1ic8Ae0uaA9wL7JbL/5P0nl2XY684FDg515/KAO6ViIjHSJ/JmaTjXmdHxKOkXWVP5ffx30jrg4i4FzgTuDW/dinpmIcNAL28+9bMyiidj39ZROww1LGYDSZvSZiZWSlvSZiZWSlvSZiZWSknCTMzK+UkYWZmpbruYjpJPshiZtaCiFjuepeuSxIAPhhvZtY/ZddDtm13U+4lcoZSb6C/kvTa3APkI0q9id4sadVcd3tJMyXdLmnfwjROytOYKmm9dsVqZma1te0U2Pyj/mJELMxdA0wmdauwbkR8rarubcD+pHsc3ApsB2wKnBoR+0iaTOp7p+FVupLCWxJmZv0jqebuprZtSUTEXyu9Q5K6Ul6axz8mabqkY3Ngo4EREbEgd9/wW2ATUjfM1+Q21wA7titWMzOrre1nNynd+ewk4OvAT0n98e8KTJK0K7A2L3fpDPBkLlurUh4RzwGr1Zh2n9JtOF8a2rYgZmY9qK1JIncVfBmpj//7I2JhRCzN9w74MenGJE+Q+qmvGJfLnqyU562N5bo4joi+iFBxaOfymJn1mnYeuBZwITA1In6ay4rJYCfg4YhYDCxVun3iaqQ7Uz1MOjZR6aZ6Lxp3E21mZgOsnafA7k46GL2x0n2FZwNPS9qddHzibtLuJ0i3jryKlLT6ImIJMF/p/rkzSP3oH9LGWM3MrIau6+DPZzeZmfVf2dlNXXkx3UEH9e8+OVOmrN+mSMzMhjf33WRmZqWcJMzMrJSThJmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrJSThJmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrJSThJmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrJSThJmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrFTbkoSkzSTNkHSrpF9Jeq2kMZKukDRd0vmSVsp1t5c0U9LtkvYtTOOkPI2pktZrV6xmZlZbO7ck/ga8JyLeAZwO/DtwBDArIiYBLwJ75rpnAZOBdwF9kkZK2gLYOiJ2BC4EjmtjrGZmVkPbkkRE/DUiFuanS4ClwCTgmlx2DTBJ0mhgREQsiIhFwG+BTWrU3bFdsZqZWW1tPyYhaQxwEvB1YC1gYX7pSWDtPCwsNKmUv1Q3Ip4DVqsx7T5JURzashBmZj2qrUlC0kjgMuCMiLiflADG5pfHAU/kYWyhWaX8pbp5a+OZ6ulHRF9EqDi0aVHMzHrSyHZNWJJIxxKmRsRPc/GtwN7Ag8BewLSIWCxpqaQNgKeBCcDDwAjgFOD8XHdGu2KtOOigx/tVf8qU9dsUiZlZZ2hbkgB2B/YHNpZ0IDCbdPD6YknTgfuAqbnuscBVpC2bvohYAsyXNEfSDGARcEgbYzUzsxraliQi4jpgTI2XDqhRdxYwsUb5CcAJAx+dmZk1wxfTmZlZKScJMzMr5SRhZmalnCTMzKyUk4SZmZVykjAzs1JOEmZmVspJwszMSjlJmJlZKScJMzMr5SRhZmalnCTMzKyUk4SZmZVykjAzs1JOEmZmVspJwszMSjlJmJlZKScJMzMr5SRhZmalnCTMzKxUwyQhaYKkVfL4LpI+K2nt9odmZmZDrZktiSuAJZI2Bb4NrANc1taozMysIzSTJJZFxFJgP+AbEXEisG57wzIzs04wsok6z0o6ETgEeIeklYCV2xuWmZl1gma2JCYD/wCOiIgFwKuAM9oalZmZdYS6WxKSRgBTI2LrSllE/AH4frsDMzOzoVd3SyIfi7gnH7Q2M7Me08wxiS2BuZLuB54BBERETGxrZGZmNuSaSRIfaHsUZmbWkRomiYj4fT428SpglfaHZGZmnaKZK673B+YA84AfAvcCF7c3LDMz6wTNnAL7FeBtwO8i4i3AdsDv2hqVmZl1hGaSxPMR8Q8ASaMiYjbwxrZGZWZmHaGZA9ePSxoH/Bz4haQngP9ta1RmZtYRGm5JRMQ+EbEwIk4ATiN17vfeRu0krSJppqSFkibnssMlPSLp5jysmsu3z3Vvl7RvYRonSZohaaqk9VpeSjMza0kzB653l7QmQETcDNwC7NLEtF8kdQr49ary8yJi5zw8l8vOInX/8S6gT9JISVsAW0fEjsCFwHFNzNPMzAZQM8ckTouIpytPIuIp0hZFXRGxLCL+XOOlj0maLulYAEmjgRERsSAiFgG/BTYBJgHX5DbXADs2EauZmQ2gZpLEiBplzRzLqOWnwObArsAkSbsCawMLC3WezGVrVcrzFsdq1ROT1CcpikOLcZmZWQ3NJIlbJF0oaTtJb5X0/4BbW5lZPraxNCJeBH4MbAs8AYwtVBuXy56slOetjWdqTK8vIlQcWonLzMxqayZJfA64Gzge+BJwD3B0KzOTVEwGOwEPR8RiYKmkDSStBkwAHiYlor1y3b2AGa3M08zMWtdMtxxLgG/loV8kXQVsDSyS9DbgGUm7A0tJieenueqxwFWkpNWX5zlf0hxJM4BFpJsemZnZIGr12EJTImK/GsUn1Kg3C1iuV9l82u1y9c3MbHA0s7vJzMx6VGmSkHRLfvz6oEVjZmYdpd7upnUk7QPsLena6hcj4vr2hWVmZp2gXpL4NHAg6ZqFg6peC8BJwsysy5UmidwFx82SZkbEDwYvJDMz6xTNHLieJum7kubn4Xx3tmdm1huaSRKXkC6g2yEP9wDesjAz6wHNJIkNI+K8iPhHHr4DbNDuwMzMbOg1kyT+JOkzktaVtI6kTwOPtTswMzMbes0kicOATYFfAjfk8cPaGZSZmXWGZvpu+htw1CDEYmZmHcbdcpiZWSknCTMzK1U3SUgaIenUwQrGzMw6S90kERFLge0keYvDzKwHNXM/iYeAmyT9jMItRCPiu22LyszMOkIzSeLxPKyZBzMz6xHNnAL7VQBJr4iIv7Q/JDMz6xQNk4SkdwNnA2OA10h6M/D5iDi03cENFwcd9HjTdadMWb+NkZiZDaxmDkifCkwCFgJExFxg6zbGZGZmHaKZJLEkIp6oPJEk0k2HzMysyzWTJH6dO/VbWdIOpK7DfVc6M7Me0EyS+BywFLgf+DxwO3BcO4MyM7PO0MzZTUskXQLcDSwD5kfEsrZHZmZmQ67hloSkA4G5pK2I44E5kvZvd2BmZjb0mrmY7qvA9hHxdwBJ6wIzgCvbGZiZmQ29Zo5J/C/wbOH5s8Af2hOOmZl1ktItidz7awB/Ie1impaf7wHMGpzwzMxsKNXb3fRAfnwQuLpQflf7wjEzs05SmiQi4pLBDMTMzDpPM2c37SnpNkl/kLRA0p8lLRiM4MzMbGg1c3bTN4EPAPMiwt1xmJn1kGbObnoUuN8Jwsys9zSzJXE8cIukmcALlcKI+Pe2RdUj3MW4mXW6ZrYkvg3cAcwnnelUGeqStIqkmZIWSpqcy8ZIukLSdEnnV+6dLWn7XPd2SfsWpnGSpBmSpkpar5UFNDOz1jWzJTEyIo5pYdovAvsBnyyUHQHMiogzJZ0L7AlcA5wFTAaeBm6VdC2wKbB1ROyYk8xxwBdaiMPMzFrUzJbEDZK+KGkLSRMqQ6NGEbEsIv5cVTyJlBTIj5MkjQZGRMSCiFgE/BbYpEbdHZtZIDMzGzjNbElslx93L5QFsGsL81uLfIc74Elg7TwsLNSplK8F/A4gIp6TtFr1xCT1ASe2EIeZmTWhma7CdxnA+T0JjAUeB8YBT+RhbKFOpbxSl7y18UyN2PqAvmKZpK4/C8sHvM1ssDRMEpJOqVXe4tlNtwJ7kw587wVMi4jFkpZK2oB0TGIC8DAwAjgFOD/XndHC/MzMbAU0s7upeCbTKqQf7OpjDTVJugrYGlgk6W3AV4CLJU0H7gOm5qrHAleRjpH0RcQSYL6kOZJmAIuAQ5qZp5mZDZxmdjf9Ux9Oki4Abmhm4hGxX43iA2rUmwVMrFF+AnBCM/MyM7OB18zuppULT1cCtgJe3a6AzMysczS7uykAAUtJ3XR8sl4DMzPrDs3sbnrNYARiZmadp96d6d5dr2FEXD/w4ZiZWSeptyVxUI2yAHYDXkk6RdXMzLpYvTvTfaQynjvi+yDweeA3wP7tD83MzIZa3WMS+UrnjwGfBqYDB0VEwx5gzcysO9Q7JvEV4DDSRW47R0TzfUGYmVlXqLcl8VVSNxmHAodIqpQLiIjYsM2xmZnZEKt3TKKZbsTNzKyLORGYmVkpJwkzMyvVTLcc1iV8Hwoz6y9vSZiZWSknCTMzK+UkYWZmpZwkzMyslJOEmZmVcpIwM7NSThJmZlbKScLMzEo5SZiZWSknCTMzK+UkYWZmpZwkzMyslJOEmZmVcpIwM7NSThJmZlbKScLMzEo5SZiZWSknCTMzK+UkYWZmpZwkzMyslJOEmZmVGjnUAVjnO+igx5uuO2XK+m2MxMwG25BsSUh6RtLNeXi/pDGSrpA0XdL5klbK9baXNFPS7ZL2HYpYzcx62VDtbvr/EbFzHn4CHAHMiohJwIvAnrneWcBk4F1AnyRv+ZiZDaKhShKvlnSLpB9KWg+YBFyTX7sGmCRpNDAiIhZExCLgt8AmQxSvmVlPGqok8dqI2An4KXAmsBawML/2JLB2HhYW2lTKXyKpT1IUhzbHbWbWU4YkSUTE3/PolcCWpAQwNpeNA57Iw9hCs0p5cTp9EaHi0M64zcx6zaAnCUmrSRqRn04CHgVuBfbOZXsB0yNiMbBU0gaSVgMmAA8PdrxmZr1sKA4EbwpcIGkRsAT4JPAYcLGk6cB9wNRc91jgKlIy64uIJUMQr7XIp86aDX+DniQi4i5gmxovHVCj7ixgYtuDMjOzmnzFtZmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrJSThJmZlXKSMDOzUk4SZmZWyknCzMxKOUmYmVkp3zPaOo67GDfrHN6SMDOzUk4SZmZWyknCzMxKOUmYmVkpJwkzMyvlJGFmZqWcJMzMrJSThJmZlfLFdNY1fBGe2cDzloSZmZVykjAzs1JOEmZmVspJwszMSvnAtfU8H/A2K+ckYdaiVpPLcGlnBt7dZGZmdThJmJlZKScJMzMr5SRhZmalfODazGryAW+DYZAkJH0SOAx4EfhoRDw8xCGZWR0+C6u7dHSSkLQ2cAQwEdgaOBXYf0iDMrOO0Z/EAi8nl8FuN5x1dJIAtgd+FRFLgd9ImjDUAZmZ9ddwTi6KiKGOoZSkg4GNIuK0/HxuRLy58HofcOIQhWdm1lUiQtVlnb4l8STwpsLzZcUXI6IP6Gt2YpKi1pvgdm43lPNyO7fr5HadfgrsLGBnSSMkbQP8dqgDMjPrJR29JRERT0i6BJhOPrtpiEMyM+spHX1MYqANh007t+uMdsMhRrdzu8Fo1+m7mwbaV93O7TpwXm7ndh3brqe2JMzMrH96bUvCzMz6wUnCzMxKOUmYmVmprk4Skj6VH98u6TZJH3K7mtP5cIPXV5N0hKTtJK0j6XRJJ0oa26DdxvlRkg6X9E1JR0tapUG7kZIOlnSgpFGF8kP7s1y5zWn9bZPbvbMfdVd4PTQTZyUmSWtKOlXS1ZLOlvSKdsQp6WuSdmhm2g2ms4aklftRv+X3M89rW0nrNlm/+PnatPKZbdBmhCRVlTVcB8X3QdKrJL2xmRir4pssaasm6rb0na0pIrp2AG7KjxcDGwIze7kdsHaNYR1S/1j12v2CdFbE6cDtwGeBDwM/bjK+U4BvApOArwA/bNDuh6TOHP8TuAMYX5xenXbzgLl5mJeHp4G5DdodUzUcC9wHHNOm9dBqnDfnxx+Qrhl6JfA+4Lo2xfkw8JP8XpwMvLHJ+RwI3A9cRuqg80HgbuCgNsV5Xn58FzAHuDDP77AG7Y4GHsif7xOA24BpwOfqtDk0L9t9wAnVMddpdzwwm3SB8DHAzcC1wJkN2t2YH48CbgS+nNfJyQ3atfSdrTV09MV0A2CMUk+ySyJigaTFPd7uT6Qf3cq/oMjjby5tkYyNiBMBJM2OiHPyeLMXN749InbK49Ml3dKg/oYRcXCex6XAFElHNTGfy4HNgP+OiNm5/dSI2LNBu4+TfhB/VChbAvytiXlC/9dDq3EuyY/rR8SFefwxSUe3Kc4/RsT787/P/YBvSFoLuCIizqjT7ljgrcAawD3ABGAxcBMwpQ1xviE/fgnYLSL+Kmk06Yf4kjrtPgS8ERgDPASMJ120OwM4u6TNvwJbktbFcZKmkBJHo2sP3hcRW0lalZSYXhcRSyTNbNCu0hXRZOCdEbEMQNL0Bu1W9Dv7kq7e3QRcRPrin5s/NL/v8XYPAftExC552DUidiH966pnVGH89CZjA5gg6Rxgo+JmPbBqg3ajJa0EEBEPkH6gvkn6sSkVEScDnwEOlvR9SZuSEmEjmwM/y/P5a0RcAvwpIr7fRFvo53pYgTinSDoPeCi3O0TS14F72xFnId6nIuKiiHgX8B7SD349z0XEooj4M2nr6OmIeAF4oU1xrqHUbc+qEfHXHPNi0g9+PYsjYllELAJ+GREvRPob/nydNstyvWWROh79BXANKSHWMyoniDVI36fK7rdGv8F/lDSRtI53Bsi7mxqtg1a/s8vr76bHcBtIK+UNbhcA2wKr1yjfuEG7vYGRVWUrA59u0G6nwjAml60JfKJBu8nVMQHjgFP78b68EjgfuL4fbVYBPg9cDdw+SOuvEue0JutvQer5+DukXXJ7kK93asPn5bD+Lk9u97Man5cRNNituQJxfq8wrFX4nF3ToN13Sj7XV9dpczFpK6BYtgfw50bvJWk31Y9Iu33mk/6cHd2g3WrAGcBMUmL4I2lrbHyDdi19Z2tOq5UPwXAZSPtDbyXtpxxZb+X3QjvSbopa5dv0crsa9dcEtmvX5wzYtqR853Yu32B9XupMb7k/KAMR53AcgNXJf5zaNP2WPmO1hm4/JnEE6WDpTZH2/43p8XY/k/Q/wLkREXlf86nAxqR/Hj3ZTtIJJeV7RMRJdeZX0d/1MFPSlcCRkXZ1VJxA2o9eptX3pdU4W30/94+IKyUdy/K70c4a6DjL1h9AvfXXSrsVmFflPTmmqpyIKH1PWp0frX/GltPtxyQqB30qH9QRPd5uR2As6eDxsaQDiTdFRKMfmG5v91ng3aT7l9xL2hVQGZrR3/UwE/hljvMthfJGBz9bXb5W42x1fk/nx78Bf68a2hFnq+uvlXatzqvynlS/H43ek1bn1+pnbHlDvdnVzoF0Kt7NpLN6rgcO6PV2pLM5ZgGPACcBI5qcV9e2Ix3kew/p1NKfAx8j79tux3rg5VM8X0/6Mn+hWN6O92WwPy8rMrTwfra0/lppt6KflRbei1aXreXP2HLTavcKH+oBWAt4C7B2r7cDTiP9G3wT6d/Z5/MPwE693K5qGpsBvwYubuN6+FVhfBTwtfxjOHsQlq/tn5eBGFbg+9Dq+ut3u1bntQLvSdPza/UzVmvoyl5g6+0Tjfr7/7q93RERcVFV2auBsyNicg+3Ww/Yn7Sf/XHSRWA3RcTSsja5Xavr4VsRcVRV2e7AWRGxeZ12rS7foH5eWrUCcba6/vrdrtV5tWoFlq2lz1jNaXVpktg9IqZJOqz6tUjnwPdkO6tN0gvAnaQrYBdT+IFq8OM0LNZDt8e5Auuv3+1anVerBnt+tXTl2U35g7YS6VS9o93OGvh4K42Gy3rogThbWn8ttmt1Xq0a7PktpyuTBEBELJO0rqSVI13t6XZW04r8mx4u66Gb42x1/bXSbrC3vDphS69rk0Q2HnhE0lzSaXUREfu6nQ2w8QyP9TAex2n91JXHJCpUo9vfiGjYX023t7OBNVzWg+O0VnT7xXSLgE8CXwQeA5rtG7/b29nAGi7rwXFav3V7kriEdCHJ5hGxhOYPAnV7OxtYw2U9OE7rt25PEqMj4mpe7off7awdhst6cJzWb92eJBZKeg+pL/d30XzfMd3ezgbWcFkPjtP6rduTxMdInZQ9BexG2s/pdjbQhst6cJzWb119dlOFpA0BImKB21m7DJf14DitP7pyS0LSpZLG5fHPkm4xOEXSF3q5nQ2s4bIeHKetkBiE3gsHewCmF8YfIt3oXMBtvdzOQ2d8zhzn8I6z14ZuveJ6JICkNwIPR8Sz+XmjsyW6vZ0NrOGyHhyntaxbk8SNkq4m3WbxywCS1ublO171ajsbWMNlPThOa1nXHrjO/0aejYhH8/O1gLGV573azgbWcFkPjtNa1bVJwszMVlxXnt1kZmYDw0nCzMxKdWWSkLSapCMkbSdpHUmnSzpR0tgWp/fhBq+PlHSwpAMljSqUH9qg3cb5UZIOl/RNSUdLWqWFGE/rbxtbMZLemR/XlHSqpKslnS3pFUMdW5Gkr0nq+J5UJW0k6UxJx0laS9J3JV0h6c1DHVsv68okQbpZ+MbAfsDVpO6GHwG+V6+RpLVrDOsAH20wv+8DbwK2AKZLGp/LD2/QrhLPfwHbAlcAazYR5zxJc/MwT9I84FNKN2mxwfOV/Pgt4GFS9xG3kD4PneR9wPGS7pN0cj443Ikqvb/+HZgF/Bg4E/j2UAbV67r1FNixEXEigKTZEXFOHm/0Y/8n4A7SBTyQbjouoNE/mQ0j4uA8j0tJV4ke1Y943x4RO+Xx6ZJuaVD/cmAz4L8jYnae79SI2LMf87QVVzl/f/2IuDCPPyap0+4j/ceIeH/ekt4P+EY+a+iKiDhjiGMrUkRcBSDp6Ii4Lo+/OLRh9bZuTRKjCuOn96PdQ8A+EfFMsVDSLxu0Gy1ppYhYFhEPSNoPuJK0NVPPBEnnABtJGhURlS/DqvUaRcTJ+fzxL0o6BjiFlNBscE2RdB7wkKTvA78kbRHeO7Rh1RYRTwEXARdJWh84YIhDqvaCpP8gbU3/Q9KRwN/wdRJDqitPgZW0NzAt0g1LKmUrA5+IiHPrtNsWeDAiFlWVbxx1bp8oaTJwZ7GOUh80x0fEl+q026nw9M6IeFbSmsAHI+K75Uv4T9N4JXACMD4idm+mjQ0cSVuQ/p1vADxJ2t00LTroiyXpsIi4ZKjjaCRv6ewP3JeHL5C25M8Nd/I3ZLoySZiZ2cDo1gPXZmY2AJwkzMyslJOEmZmVcpIwM7NSThJmZlbKScK6iqQXJc3Ow0xJr8vlh0sKSVsX6p6ay0ZLOrd4saWkP1U9/2M+rbmjSbqjcMV/rdd3lnTZIIZkw5yThHWbv0fEVhGxFXAhcEzhtfmk8/ArdgUq59/fAewAL1178teq54siYuFABCipWy9itS7kJGHdbBzwdOH59cBuAHmLYj5Qucr9dmD7PL4D8APgDYXnd1RPXNKGkq6VNEfSXfn56yRNl3S3pF9XOqfLWzKXSrqOlLyK0zlc0uWSbpT0qKT35s4e75d0YaHeRyTdm4dP5LIRki7IdS8HVi7U/7ikO3MfX8td1Cnp3yQ9kOP/enNvqfUa/6OxbrOOpNnAasDq5K2B7AXgQUlbkrYofkTamiAiHpG0nqQ1cpufAO8uPF8uSQDnkPo/uljSqqSuUVYCdouI5yVtQ+oWptKn1luBbaqv6M82A7YjJabbScnss8BvJE0AngG+lKexDLhT0vW5zbiI2Cwv193w0pXgu5ESn4CpSrcGLfoysFFEPKcWe0i27uctCes2ld1Nrwc+A1xQ9fqVwGTSD+gNVa/dCbwF2Ib0Y/ub/Hx7aieJt5F6LiUinouIxaR/8hflnnkvAoo9rk4rSRAAN+T284DFETEzd+0xH9iIlBxuiIinIuIfwLU5romk3oOJiDnAA3l6u+TX7gbuAl4LvL5qnncD35d0IPB8SVzW45wkrJtdDexYVTYNOAS4PyJeqHrtjlx/VP7BnpWfv4HmO+37HKnb8DfntsV7gzxTs0XyAkBELKuMZ8tIW/zinztxVNVjrfLzKsdnImKTiPhxVd29gPNJCeW6egtlvctJwrrZROB3xYKIeB74Iuk+BdVuB44g/ZuHlCSOAO6LiKUl9Q8BkLSqpNGkHkwX5K2AwwdgGSp+DeymdIOj1YE9cny3kXtzzbubKsdRbgI+WDkjS9LGxV1KklYCXhURN5AO7m82gLFaF/ExCes2lWMSIt3v4RPVFSKi7BTQXwOvzo9ExF8kQe1dTZCOGVwo6fOkf//7km6Qc5Wkw4GpLS/F8jE/Jul00k15AM6OiEcl/ZF07GQeaffY7Fz/XklnArcqLcRTpN5qK0YAP8zHXEQ6PmG2HPcCa2Zmpby7yczMSjlJmJlZKScJMzMr5SRhZmalnCTMzKyUk4SZmZVykjAzs1JOEmZmVur/AK+asABl07NwAAAAAElFTkSuQmCC\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "sns.barplot(x='model', y='No_of_cars', data=model_count, color='blue', alpha=0.75)\n",
    "plt.title(\"Number of cars present for each model\")\n",
    "plt.xlabel(\"BMW car models\")\n",
    "plt.ylabel(\"Number of cars\")\n",
    "plt.xticks(rotation=90)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Can you plot the above barplots side by side?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 100,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 1080x360 with 3 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "sns.set_context('paper')\n",
    "\n",
    "plt.figure(figsize=(15,5))\n",
    "\n",
    "plt.subplot(1,3,1)\n",
    "sns.barplot(x='model', y='% of cars', data=model_count, color='blue', alpha=0.75)\n",
    "plt.title(\"Number of cars present for each model\")\n",
    "plt.xlabel(\"BMW car models\")\n",
    "plt.ylabel(\"Percent of cars (%)\")\n",
    "plt.xticks(rotation=90)\n",
    "plt.yticks(np.arange(0,101,10).tolist())\n",
    "\n",
    "plt.subplot(1,3,2)\n",
    "sns.barplot(x='transmission', y='% of cars', data=transmission_count, color='orange')\n",
    "plt.title(\"Number of cars present for each transmission type\")\n",
    "plt.xlabel(\"Type of transmission\")\n",
    "plt.ylabel(\"Percent of cars (%)\")\n",
    "plt.yticks(np.arange(0,101,10).tolist())\n",
    "\n",
    "plt.subplot(1,3,3)\n",
    "sns.barplot(x='fuel_type', y='% of cars', data=fuelType_count, color='green', alpha=0.75)\n",
    "plt.title(\"Number of cars present for each fuelType\")\n",
    "plt.xlabel(\"Type of fuel\")\n",
    "plt.ylabel(\"Percent of cars (%)\")\n",
    "plt.yticks(np.arange(0,101,10).tolist())\n",
    "\n",
    "plt.suptitle(\"Categorical variables in the BMW used cars dataset\")\n",
    "plt.tight_layout()\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Create a function to find the number of observations for unique value in a column of a DataFrame"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 101,
   "metadata": {},
   "outputs": [],
   "source": [
    "def unique_val_count(data, column):\n",
    "    df_count = df[column].value_counts()\n",
    "    df_count = pd.DataFrame(df_count)\n",
    "    df_count = df_count.reset_index()\n",
    "    df_count = df_count.rename(columns={'index':column, column:'No_of_cars'})\n",
    "    df_count['% of cars'] = np.round(((df_count['No_of_cars']/df_count['No_of_cars'].sum())*100), 2)\n",
    "    \n",
    "    return df_count"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 102,
   "metadata": {},
   "outputs": [],
   "source": [
    "model_count = unique_val_count(df, 'model')\n",
    "year_count = unique_val_count(df, 'year')\n",
    "transmission_count = unique_val_count(df, 'transmission')\n",
    "fuelType_count = unique_val_count(df, 'fuelType')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 103,
   "metadata": {},
   "outputs": [],
   "source": [
    "# sort the year_count DataFrame based on 'year'\n",
    "year_count = year_count.sort_values(by='year')\n",
    "# year_count"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Create a function to show the number of observations for each unique value in a column using a barplot"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 104,
   "metadata": {},
   "outputs": [],
   "source": [
    "def barplot(data, column_x, color, rotation, yticks):\n",
    "    \n",
    "    # create a barplot using seaborn\n",
    "    sns.barplot(x=column_x, y='% of cars', data=data, color=color, alpha=0.75)\n",
    "    \n",
    "    # write a title for your plot\n",
    "    plt.title(\"Number of cars present for each \" + column_x)\n",
    "    \n",
    "    # write proper lebel for the x and y axis\n",
    "    plt.xlabel(column_x)\n",
    "    plt.ylabel(\"Percent of cars (%)\")\n",
    "    \n",
    "    # rotate the xticks if necessary\n",
    "    plt.xticks(rotation=rotation)\n",
    "    \n",
    "    # provide a range for the yticks\n",
    "    plt.yticks(yticks)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 105,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 1080x720 with 4 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "sns.set_context('talk')\n",
    "\n",
    "plt.figure(figsize=(15,10))\n",
    "\n",
    "# row 1, column 1\n",
    "plt.subplot(2,2,1)\n",
    "barplot(model_count, 'model', 'blue', 90, np.arange(0,51,10))\n",
    "\n",
    "# row 1, column 2\n",
    "plt.subplot(2,2,2)\n",
    "barplot(year_count, 'year', 'orange', 90, np.arange(0,51,10))\n",
    "\n",
    "# row 2, column 1\n",
    "plt.subplot(2,2,3)\n",
    "barplot(transmission_count, 'transmission', 'green', 0, np.arange(0,71,10))\n",
    "\n",
    "# row 2, column 2\n",
    "plt.subplot(2,2,4)\n",
    "barplot(fuelType_count, 'fuelType', 'red', 0, np.arange(0,71,10))\n",
    "\n",
    "# write the title for all the plots\n",
    "plt.suptitle(\"Categorical variables in the BMW used cars dataset\")\n",
    "\n",
    "# keep the individual plots separate from each other\n",
    "plt.tight_layout()\n",
    "\n",
    "# display the plots\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
